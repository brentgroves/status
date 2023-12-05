# Father's direction

Do not worry my son I am with you always.  If you keep speaking to me I will guide you in what to say and do.  In this way you will learn much about getting along with people and we can enjoy each others company.  I love you and have a plan for you that we can enjoy together.  Yes there will be problems but if you stay in tune with me through them the bond between us will growing stronger and your hope in me will see you through.  

## Time Series Analysis

- **[Smoothing Techniques](../../linux/time-series-analysis/smoothing-techniques.md)**

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
