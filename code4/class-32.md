# Read: 32 - Serverless and Amplify

## serverless 

* serverless doesn't mean that there is no server; it means that the developer don't need to care about writing code, creating or maintaining the server; these stuff will be managed by a host. 
* Serverless is a cloud computing execution model where the cloud provider dynamically manages the allocation and provisioning of servers.
* Serverless applications are event-driven cloud-based systems where application development rely solely on a combination of third-party services, client-side logic and cloud-hosted remote procedure calls (Functions as a Service).

### traditional server vs Serverless:
1. cost: Serverless is reduced cost that traditional server.
2. Networking: Serverless functions are accessed only as private APIs, means we cannot directly access them through the usual IP; so traditional server is better here.
3. 3rd Party Dependencies:  For simple applications with few dependencies, Serverless is the winner; for anything more complex, Traditional Architecture is the winner.
4. Environments: serverless is easier here and better.
5. Timeout: Traditional Architecture is better.

***

## AWS Amplify

* AWS Amplify is a set of tools and services that can be used together or on their own, to help front-end web and mobile developers build scalable full stack applications, powered by AWS. With Amplify, you can configure app backends and connect your app in minutes, deploy static web apps in a few clicks, and easily manage app content outside the AWS console.

### Benefits:
1. Configure backends fast
2. Seamlessly connect frontends
3. Deploy in a few clicks
4. Easily manage content

### Features & Tools

1. Authentication
2. API (GraphQL, REST)
3. Storage
4. Interactions
5. PubSub
6. DataStore
7. Functions
8. Analytics
9. AI/ML Predictions
10. Push Notifications
11. Managed Hosting
12. CI/CD
13. PR Previews
14. Monitoring
15. Custom Domains
16. Manage Users
17. Manage Content

***

## GraphQL 

* The GraphQL Transform provides a simple to use abstraction that helps you quickly create backends for your web and mobile applications on AWS. With the GraphQL Transform, you define your application’s data model using the GraphQL Schema Definition Language (SDL) and the library handles converting your SDL definition into a set of fully descriptive AWS CloudFormation templates that implement your data model.
