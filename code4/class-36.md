# Read: 36 - Cognito

* Amazon Cognito is a simple user identity and data synchronization service that helps you securely manage and synchronize app data for your users across their mobile devices. You can create unique identities for your users through a number of public login providers (Amazon, Facebook, and Google) and also support unauthenticated guests. You can save app data locally on users’ devices allowing your applications to work even when the devices are offline. With Amazon Cognito, you can save any kind of data in the AWS Cloud, such as app preferences or game state, without writing any backend code or managing any infrastructure. This means you can focus on creating great app experiences instead of having to worry about building and managing a backend solution to handle identity management, network state, storage, and sync.


* The Amplify Auth category provides an interface for authenticating a user. Behind the scenes, it provides the necessary authorization to the other Amplify categories. It comes with default, built-in support for Amazon Cognito User Pool and Identity Pool. The Amplify CLI helps you to create and configure the auth category with an authentication provider.

* To setup and configure your application with Amplify Auth and go through a simple api to check the current auth session

* To start provisioning auth resources in the backend, go to your project directory and execute the command:

```amplify add auth```

* Enter the following when prompted:

```
? Do you want to use the default authentication and security configuration?
    `Default configuration`
? How do you want users to be able to sign in?
    `Username`
? Do you want to configure advanced settings?
    `No, I am done.`
```

* To push your changes to the cloud, execute the command:

```amplify push```

* Upon completion, amplifyconfiguration.json should be updated to reference provisioned backend auth resources. Note that these files should already be a part of your project if you followed the Project setup walkthrough.

* Add the following dependency to your app's build.gradle along with others you added above in Prerequisites and click "Sync Now" when prompted:

```
dependencies {
    implementation 'com.amplifyframework:aws-auth-cognito:1.24.0'
}
```

* Add the Auth plugin before calling Amplify.configure. Update the code you added in Prerequisites:

```java // Add this line, to include the Auth plugin. Amplify.addPlugin(new AWSCognitoAuthPlugin()); Amplify.configure(getApplicationContext()); ```

* We can now check the current auth session.
* For testing purposes, you can run this from your MainActivity's onCreate method.

```
Amplify.Auth.fetchAuthSession(
    result -> Log.i("AmplifyQuickstart", result.toString()),
    error -> Log.e("AmplifyQuickstart", error.toString())
);
```







