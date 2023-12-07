# Father's direction

Do not worry my son I am with you always.  If you keep speaking to me I will guide you in what to say and do.  In this way you will learn much about getting along with people and we can enjoy each others company.  I love you and have a plan for you in which we can enjoy spending time together.  Yes there will be problems but if you stay in tune with me then through them the bond between us will continue growing stronger and your hope in me will see you through anything.  

## Start here

<https://go.dev/tour/flowcontrol/1>

Add Brad rank function
Add Kevin Proxmox

## Report System and Group Tech Share

- Install Prometheus and Grafana with example
- Share anything group might find interesting.

<https://stackoverflow.com/questions/45751608/why-is-http-client-prefixed-with>

## Gage report and plex admin, Intelliplex, or SQL tech share from anyone

- Plex admin, Intelliplex, or SQL tech share from anyone

## Time Series Analysis

- **[What is a moving average, MA](../../linux/time-series-analysis/smoothing-techniques.md)**

- **[Double Moving Averages for a Linear Trend Process](./exponential_smoothing.md)**

Unfortunately, neither the mean of all data nor the moving average of the most recent M values, when used as forecasts for the next period, are able to cope with a significant trend.

There exists a variation on the MA procedure that often does a better job of handling trend. It is called Double Moving Averages for a  Linear Trend Process. It calculates a second moving average from the original moving average, using the same value for M. As soon as both single and double moving averages are available, a computer routine uses these averages to compute a slope and intercept, and then forecasts one or more periods ahead.

**[MA Calculator](https://mathcracker.com/moving-average-forecast-calculator)**

**[Double MA Tutorial](https://medium.com/@polanitzer/time-series-methodologies-part-3-double-moving-average-6aba4a5fbb7e)**

## Alert Manager

Another part of working with our report system metrics besides Prometheus and Grafana is the alert manager.  In order to do something useful when a problem is detected the alert manager is configured to post to a webhook.  We can implement a webhook to send an email or a message in Microsoft teams or anything else we want.

## What are webhooks?

<https://dev.to/koladev/building-a-robust-webhook-server-with-golang-a-comprehensive-guide-4oa0>

<https://github.com/adnanh/webhook>
Webhooks are automated messages sent from one system to another triggered by specific events. They are used to notify other systems in real time when something happens, without the need for continuous polling. In a payment gateway situation, when you make a payment request, you can poll onto an endpoint with the id or the reference of the transaction to get the updated status. This method has its own drawbacks because you can be limited to the number of requests you can make (throttle), and there can be server timeout for example.

**[webhooks](../../linux/webhook/webhook.md)**

## Use Golang for report runner

The report runner is pulling report requests from a queue and starting the ETL process.

- Efficient Scheduling: Golang's runtime takes care of scheduling goroutines on the available CPU cores, ensuring optimal utilization. A machine with 4 cores can run thousands of goroutines concurrently, thanks to the efficient scheduling algorithm. Here is a simple usage of goroutines in Golang

```golang
func main() {
    for i := 0; i < 10000; i++ {
        go printNumber(i)
    }
}

func printNumber(number int) {
    fmt.Println(number)
}
```

This code will spawn 10,000 goroutines to print numbers concurrently.

## Report System Architecture

## Report Requestor

## Report Runner

## Webhooks

- The Report Requestor Web App subscribes to a user channel through a websocket.
- The Report Runner calls the Report Requestor's webhook with the report result as a payload.
- The Report Requestor API publishes the report result to the the appropriate user channel thereby notifying the customer to the results of there report request.

Here's a diagram representing the restaurant analogy for queuing with channels in Golang:

![queue](https://res.cloudinary.com/practicaldev/image/fetch/s--JVAjUJYJ--/c_limit%2Cf_auto%2Cfl_progressive%2Cq_auto%2Cw_800/https://cdn.hashnode.com/res/hashnode/image/upload/v1692046719251/ec0c2f67-2e07-4974-8e57-d1327c33d6ee.png)

In this queue system the metric system can post to the Report Runner's webhook adding or subtracting goroutines as report requests change.

## **[Uptrace Open-Telemetry](https://github.com/uptrace/uptrace)**

Uptrace is an open source APM that supports distributed tracing, metrics, and logs. You can use it to monitor applications and troubleshoot issues.

Uptrace comes with an intuitive query builder, rich dashboards, alerting rules, notifications, and integrations for most languages and frameworks.

Uptrace can process billions of spans and metrics on a single server and allows you to monitor your applications at 10x lower cost.

Uptrace uses OpenTelelemetry framework to collect data and ClickHouse database to store it. Uptrace also requires PostgreSQL database to store metadata such as metric names and alerts.

Features:

- Single UI for traces, metrics, and logs.
- SQL-like query language to aggregate spans.
- Promql-like language to aggregate metrics.
- Built-in alerts with notifications via Email, Slack, WebHook, and AlertManager.
- Pre-built metrics dashboards.
- Multiple users/projects via YAML config.
- Single sign-on (SSO) using OpenID Connect: Keycloak, Google Cloud, and Cloudflare.
- Ingestion using OpenTelemetry, Vector, FluentBit, CloudWatch, and more.
- Efficient processing: more than 10K spans / second on a single core.
- Excellent on-disk compression: 1KB span can be compressed down to ~40 bytes.
