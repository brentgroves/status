# Father's direction

Do not worry my son I am with you always.  If you keep speaking to me I will guide you in what to say and do.  In this way you will learn much about getting along with people and we can enjoy each others company.  I love you and have a plan for you in which we can enjoy spending time together.  Yes there will be problems but if you stay in tune with me then through each hardship the bond between us will continue growing stronger and your hope in me will see you through anything and everything.  

## Start here

<https://go.dev/tour/flowcontrol/1>

**[webhook tutorial](../../volumes/go/tutorials/webhook/webhook.md)**

**[gage report](../../volumes/sql/gages/gage_cali_next_calibration.sql)**

What services through Azure DW, AKS, SMTP server, or Azure Portal access to send email.

Tuition Assistance.

Returning students for the elderly.

Days off:

Add Brad rank function
Good morning dear ones,

I hope you and your loved ones are staying healthy during this cold season!  It is a privilege to work with each one of you :-) As always please feel free to get in touch with me about anything at home or at work.

-Sincerely yours,
Brent
260-564-4868

- Plan to work on the gage_record view self-join next
- Work on the webhook system for the report requestor.
- Switched from a database to using redis for communication between the report reqestor and runner.
- Came across Multipass and JuJu/charms that can be used to manage the life-cycle of VMs and applications identically on a variety of cloud providers.

## Multipass

<https://multipass.run/docs#:~:text=Multipass%20is%20a%20tool%20to,your%20own%20local%20mini%2Dcloud>.

Multipass is a tool to generate cloud-style Ubuntu VMs quickly on Linux, macOS, and Windows. It gives you a simple but powerful CLI that allows you to quickly access an Ubuntu command line or create your own local mini-cloud.

Cloud-style VMs at your fingertips
Spin up cloud instances with a single command

Launch instances of Ubuntu and initialise them with cloud-init metadata in the same way you would on AWS, Azure, Google, IBM and Oracle. Simulate your own cloud deployment on your workstation.

## JuJu

JuJu manages the life-cycle of software deployed to public clouds using charms.

### Juju supports all of the following clouds

Amazon EC2
Amazon EKS
Equinix Metal
Google GCE
Google GKE
LXD
MAAS
Manual
MicroK8s
Microsoft Azure
Microsoft AKS
OpenStack (see also the OpenStack website; or MicroStack)
Oracle OCI
VMware vSphere

<https://juju.is/docs/juju/tutorial>

- Use Multipass to launch an Ubuntu VM with the charm-dev blueprint

```bash
multipass launch --cpus 4 --memory 8G --disk 30G --name tutorial-vm charm-dev
```

Use multipass shell tutorial-vm to open a shell into the VM. Sample session:

```bash
multipass shell tutorial-vm
```

Your VM comes with MicroK8s preinstalled.
Your VM comes with the Juju CLI client preinstalled.

Add your cloud definition to Juju
Juju has automatically used your MicroK8s’s .kube/config file to define a cloud called microk8s.

Run juju clouds to verify. Sample session:

```bash
ubuntu@tutorial-vm:~$ juju clouds
Only clouds with registered credentials are shown.
There are more clouds, use --all to see them.

Clouds available on the controller:
Cloud     Regions  Default    Type
microk8s  1        localhost  k8s  

Clouds available on the client:
Cloud      Regions  Default    Type  Credentials  Source    Description
localhost  1        localhost  lxd   1            built-in  LXD Container Hypervisor
microk8s   1        localhost  k8s   1            built-in  A Kubernetes Cluster

```

LXD is a system container and virtual machine manager

## Report System and Tech Share

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

## The architecture of the report system

The architecture of the solution is almost the same as this Payment Gateway:

We have an API that acts as a Payment Gateway. A request on the endpoint of this API will return a payload but this payload is also sent through a Redis channel called payments. Thus all services listening to this channel will receive the data sent.
We then have the webhook service written in Golang. This service listens to the payments Redis channel. If data is received, the payload is formatted to be sent to the URL indicated on the payload. If the request fails due to timeout or any other errors, there is a retry mechanism using Golang channel queuing and exponential backoff to retry the request.

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
