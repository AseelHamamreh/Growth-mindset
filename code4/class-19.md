# Read: 19 - Spring and Sockets

 to build a server that accepts a message that carries a user’s name. In response, the server will push a greeting into a queue to which the client is subscribed:

 1. Initialize new project with the following dependences: 

 ```
 	implementation 'org.springframework.boot:spring-boot-starter-websocket'
	implementation 'org.webjars:webjars-locator-core'
	implementation 'org.webjars:sockjs-client:1.0.2'
	implementation 'org.webjars:stomp-websocket:2.3.3'
	implementation 'org.webjars:bootstrap:3.3.7'
	implementation 'org.webjars:jquery:3.1.1-1'
	testImplementation 'org.springframework.boot:spring-boot-starter-test'
```

2. Create a Resource Representation Class

Now that you have set up the project and build system, you can create your STOMP message service.

Begin the process by thinking about service interactions.

The service will accept messages that contain a name in a STOMP message whose body is a JSON object. If the name is Fred, the message might resemble the following:

```
{
    "name": "Fred"
}
```

To model the message that carries the name, you can create a plain old Java object with a name property and a corresponding getName() method, as the following listing (from src/main/java/com/example/messagingstompwebsocket/HelloMessage.java) shows:

```
package com.example.messagingstompwebsocket;

public class HelloMessage {

  private String name;

  public HelloMessage() {
  }

  public HelloMessage(String name) {
    this.name = name;
  }

  public String getName() {
    return name;
  }

  public void setName(String name) {
    this.name = name;
  }
}
```

Upon receiving the message and extracting the name, the service will process it by creating a greeting and publishing that greeting on a separate queue to which the client is subscribed. The greeting will also be a JSON object, which as the following listing shows:

```
{
    "content": "Hello, Fred!"
}
```

To model the greeting representation, add another plain old Java object with a content property and a corresponding getContent() method, as the following listing (from src/main/java/com/example/messagingstompwebsocket/Greeting.java) shows:

```
package com.example.messagingstompwebsocket;

public class Greeting {

  private String content;

  public Greeting() {
  }

  public Greeting(String content) {
    this.content = content;
  }

  public String getContent() {
    return content;
  }

}
```


3. Create a Message-handling Controller

In Spring’s approach to working with STOMP messaging, STOMP messages can be routed to @Controller classes. For example, the GreetingController (from src/main/java/com/example/messagingstompwebsocket/GreetingController.java) is mapped to handle messages to the /hello destination, as the following listing shows:

```
package com.example.messagingstompwebsocket;

import org.springframework.messaging.handler.annotation.MessageMapping;
import org.springframework.messaging.handler.annotation.SendTo;
import org.springframework.stereotype.Controller;
import org.springframework.web.util.HtmlUtils;

@Controller
public class GreetingController {


  @MessageMapping("/hello")
  @SendTo("/topic/greetings")
  public Greeting greeting(HelloMessage message) throws Exception {
    Thread.sleep(1000); // simulated delay
    return new Greeting("Hello, " + HtmlUtils.htmlEscape(message.getName()) + "!");
  }

}
```


4. Configure Spring for STOMP messaging

Now that the essential components of the service are created, you can configure Spring to enable WebSocket and STOMP messaging.

Create a Java class named WebSocketConfig that resembles the following listing (from src/main/java/com/example/messagingstompwebsocket/WebSocketConfig.java):

```
package com.example.messagingstompwebsocket;

import org.springframework.context.annotation.Configuration;
import org.springframework.messaging.simp.config.MessageBrokerRegistry;
import org.springframework.web.socket.config.annotation.EnableWebSocketMessageBroker;
import org.springframework.web.socket.config.annotation.StompEndpointRegistry;
import org.springframework.web.socket.config.annotation.WebSocketMessageBrokerConfigurer;

@Configuration
@EnableWebSocketMessageBroker
public class WebSocketConfig implements WebSocketMessageBrokerConfigurer {

  @Override
  public void configureMessageBroker(MessageBrokerRegistry config) {
    config.enableSimpleBroker("/topic");
    config.setApplicationDestinationPrefixes("/app");
  }

  @Override
  public void registerStompEndpoints(StompEndpointRegistry registry) {
    registry.addEndpoint("/gs-guide-websocket").withSockJS();
  }

}
```

5. Create a Browser Client

With the server-side pieces in place, you can turn your attention to the JavaScript client that will send messages to and receive messages from the server side.

Create an index.html file similar to the following listing (from src/main/resources/static/index.html):

```
<!DOCTYPE html>
<html>
<head>
    <title>Hello WebSocket</title>
    <link href="/webjars/bootstrap/css/bootstrap.min.css" rel="stylesheet">
    <link href="/main.css" rel="stylesheet">
    <script src="/webjars/jquery/jquery.min.js"></script>
    <script src="/webjars/sockjs-client/sockjs.min.js"></script>
    <script src="/webjars/stomp-websocket/stomp.min.js"></script>
    <script src="/app.js"></script>
</head>
<body>
<noscript><h2 style="color: #ff0000">Seems your browser doesn't support Javascript! Websocket relies on Javascript being
    enabled. Please enable
    Javascript and reload this page!</h2></noscript>
<div id="main-content" class="container">
    <div class="row">
        <div class="col-md-6">
            <form class="form-inline">
                <div class="form-group">
                    <label for="connect">WebSocket connection:</label>
                    <button id="connect" class="btn btn-default" type="submit">Connect</button>
                    <button id="disconnect" class="btn btn-default" type="submit" disabled="disabled">Disconnect
                    </button>
                </div>
            </form>
        </div>
        <div class="col-md-6">
            <form class="form-inline">
                <div class="form-group">
                    <label for="name">What is your name?</label>
                    <input type="text" id="name" class="form-control" placeholder="Your name here...">
                </div>
                <button id="send" class="btn btn-default" type="submit">Send</button>
            </form>
        </div>
    </div>
    <div class="row">
        <div class="col-md-12">
            <table id="conversation" class="table table-striped">
                <thead>
                <tr>
                    <th>Greetings</th>
                </tr>
                </thead>
                <tbody id="greetings">
                </tbody>
            </table>
        </div>
    </div>
</div>
</body>
</html>
```

6. Make the Application Executable

Spring Boot creates an application class for you. In this case, it needs no further modification. You can use it to run this application. The following listing (from src/main/java/com/example/messagingstompwebsocket/MessagingStompWebsocketApplication.java) shows the application class:

```
package com.example.messagingstompwebsocket;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class MessagingStompWebsocketApplication {

  public static void main(String[] args) {
    SpringApplication.run(MessagingStompWebsocketApplication.class, args);
  }
}
```


