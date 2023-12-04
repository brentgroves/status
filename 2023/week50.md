# Father's direction

Do not worry my son I am with you always.  If you keep speaking to me I will guide you in what to say and do.  In this way you will learn much about getting along with people and we can enjoy each others company.  I love you and have a plan for you that we can enjoy together.  Yes there will be problems but if you stay in tune with me through them the bond between us will growing stronger and your hope in me will see you through.  

## Time Series Analysis

- **[Smoothing Techniques](../../linux/time-series-analysis/smoothing-techniques.md)**

## What are webhooks?

<https://dev.to/koladev/building-a-robust-webhook-server-with-golang-a-comprehensive-guide-4oa0>

<https://github.com/adnanh/webhook>
Webhooks are automated messages sent from one system to another triggered by specific events. They are used to notify other systems in real time when something happens, without the need for continuous polling. In a payment gateway situation, when you make a payment request, you can poll onto an endpoint with the id or the reference of the transaction to get the updated status. This method has its own drawbacks because you can be limited to the number of requests you can make (throttle), and there can be server timeout for example.

The diagram below illustrates the action of polling and scenarios that can happen such as throttle and server timeout:

![web_polling](https://res.cloudinary.com/practicaldev/image/fetch/s--GghB1Ocy--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://cdn.hashnode.com/res/hashnode/image/upload/v1692046743110/a5885f8f-339e-4445-af51-5477fae354ca.png)

Here is a description of the diagram above :

Client Requests Payment Status: The client repeatedly requests the payment status from the payment gateway server.

Server Responds with Payment Status: The server responds with the current payment status.

Throttle Limit Reached: After a certain number of requests, the server may throttle the client, limiting further requests.

Server Timeout: If the server is unable to respond within a certain time frame, it may result in a timeout error. Following the issues of throttling and server timeouts, businesses to be more reliable and fast combines allows their client to poll but also to receive webhooks. What happens is that, if a webhook is not received after a certain amount of time, the client can start polling to retrieve the status. This gives the client many ways to get updates on a payment but also helps the business stay more reliable, robust, and developer friendly.

Here's a diagram that illustrates the process of using webhooks first, and then falling back to polling if the webhooks are not delivered:

![webhook_polling](https://res.cloudinary.com/practicaldev/image/fetch/s--0FQyl_hK--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://cdn.hashnode.com/res/hashnode/image/upload/v1692046767883/67eb6e83-bb54-42e4-9813-2a962f653301.png)

Here is a description of the diagram above :

Client Requests Payment: The client initiates a payment request to the server.

Server Initiates Payment: The server acknowledges the payment initiation and begins processing.

Server Sends Webhook: The server attempts to send a webhook to the client with the payment status.

Webhook Not Received: If the webhook is not delivered to the client after a certain time, a note is made of this failure.

Client Starts Polling: The client, noticing the absence of the webhook, starts polling the server for the payment status.

Server Responds with Payment Status: The server responds to the polling request with the payment status.

Fallback to Polling: The entire process demonstrates a fallback mechanism where the client can resort to polling if the webhook is not received.

This approach ensures that the client has multiple ways to get updates on a payment, making the system more reliable, robust, and developer-friendly.

Most of the time, webhooks are HTTP POST requests made on a callback URL provided by the client. When a specified event occurs in System A, it triggers an HTTP POST request to a specific URL in System B. The request usually contains a payload with information about the event. System B's server then processes the request and takes appropriate action.

Now that we understand more about webhooks, let's discuss the challenges that come with designing a webhook service.

Difficulties of designing a Webhook service
Designing a webhook service is a complex task that requires careful consideration of various factors to ensure scalability, reliability, and security. Here's an in-depth look at some of the key challenges:
