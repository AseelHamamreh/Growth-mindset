# Class-06 reading Summary

## NODE.JS

**Node** is a JS runtime built on V8. Rather than thinking about it as something completely different, think of it more like a JS library that enhances base JS. Because it is utilizing a specific element of the browser (one runtime at a time) you can write more modern code and have it handle the automation to make it work. So things like template literal or destructuring can be used even on some older browsers. It also is associated with npm. Making sure you have a consistent (and changeable) version manager as testing multiple versions will be needed for legacy support checks. 

The real power comes in utilizing the browser renderer and the event based nature of the language to have the server side return a promise for information that can be filled when returned - allowing for the code to almost run parallel. To do so requires a little change on how you build some functions. A call and response is a necessity for communicating with the server. async await is the standardization of this. Because the foundation is on event listeners and discreet updates Node is best suited for projects that require a lot of real  time rendering of information (video streaming as well. That being said, it will handle most anything - those are just where it’s strengths are. check out Larval or Rails for more functionality on base runtimes - less need for additional npm for frameworks

Because it has a modern syntax you can break apart bits of code to fed to the server, along with different languages - including handling JSON. So you can feed data to multiple layers, rather than needing as many worker functions. 

![nodes](https://www.ultimateserv.com/wp-content/uploads/2020/11/Install-Nodejs-on-centos.png)