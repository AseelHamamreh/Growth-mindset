# Read: 39 - Kinesis

* The Analytics category enables you to collect analytics data for your App. The Analytics category comes with built-in support for Amazon Pinpoint and Amazon Kinesis (Kinesis support is currently only available in the Amplify JavaScript library).

* Run the following command in your project's root folder. The CLI will prompt configuration options for the Analytics category such as Amazon Pinpoint resource name and analytics event settings.

```amplify add analytics```

* To deploy your backend, run:

````amplify push````

* Upon completion, amplifyconfiguration.json should be updated to reference provisioned backend analytics resources. Note that these files should already be a part of your project if you followed the Project setup walkthrough.

##### Install Amplify Libraries
Expand Gradle Scripts, open build.gradle (Module: app). You will already have configured Amplify by following the steps in the Project Setup walkthrough.

Add Analytics by adding these libraries into the dependencies block:

```
dependencies {
    // Add these lines in `dependencies`
    implementation 'com.amplifyframework:aws-analytics-pinpoint:1.24.0'
    implementation 'com.amplifyframework:aws-auth-cognito:1.24.0'
}
```

* To initialize the Amplify Auth and Analytics categories you call Amplify.addPlugin() method for each category. To complete initialization call Amplify.configure().

Add the following code to your onCreate() method in your application class:

```
Amplify.addPlugin(new AWSCognitoAuthPlugin());
Amplify.addPlugin(new AWSPinpointAnalyticsPlugin(this));
```

* Record events
To record an event, create an AnalyticsEvent and call Amplify.Analytics.recordEvent() to send it:

```
AnalyticsEvent event = AnalyticsEvent.builder()
    .name("PasswordReset")
    .addProperty("Channel", "SMS")
    .addProperty("Successful", true)
    .addProperty("ProcessDuration", 792)
    .addProperty("UserAge", 120.3)
    .build();

Amplify.Analytics.recordEvent(event);
```

###### View Analytics console
From the terminal run the following command. Navigate to the Analytics tab, and then choose View in Pinpoint.

```amplify console analytics```

***

### Record event
* The Amplify analytics plugin also makes it easy to record custom events within the app. The plugin handles retry logic in the event the device loses network connectivity and automatically batches requests to reduce network bandwidth.

```
AnalyticsEvent event = AnalyticsEvent.builder()
    .name("PasswordReset")
    .addProperty("Channel", "SMS")
    .addProperty("Successful", true)
    .addProperty("ProcessDuration", 792)
    .addProperty("UserAge", 120.3)
    .build();

Amplify.Analytics.recordEvent(event);
```

* Events have default configuration to flush out to the network every 30 seconds. If you would like to change this, update amplifyconfiguration.json with the value in milliseconds you would like for autoFlushEventsInterval. This configuration will flush events every 10 seconds:

```
{
    "UserAgent": "aws-amplify-cli/2.0",
    "Version": "1.0",
    "analytics": {
        "plugins": {
            "awsPinpointAnalyticsPlugin": {
                "pinpointAnalytics": {
                    "appId": "AppID",
                    "region": "Region"
                },
                "pinpointTargeting": {
                    "region": "Region"
                },
                "autoFlushEventsInterval": 10000
            }
        }
    }
}
```

* To manually flush events, call:

```Amplify.Analytics.flushEvents();```