# Week48

## Fathers Will

I love you my son and look forward to the time we get to spend together today.  Entrust yourself to me and no one else and I will give you peace and happiness in whatever I have you doing.  Remember the abilities and gifts you have been given are all from me as well as your trials and hardships.  I am in control of every situation you face so do not fear because I love you like no other.  Even your troubles have a purpose for good and no matter what you are doing you will have joy as long as you stay close to me and try your best :-)

Good morning dear ones,
I hope your Thanksgiving holiday was enjoyable and relaxing!  Mine was good but I would like to get back to the steady schedule of a normal week :-) As always please feel free to contact me at home or work about anything that you need!

-Sincerely yours,
Brent
260-564-4868

## Monitoring is a key pillar of DevOps best practices

to ensure performance and health. In a distributed environment such as Kubernetes and microservices, it is even more true. This tutorial shows you how to build effectively a modern monitoring stack with Prometheus & Grafana on Kubernetes.

Monitoring is a key pillar of DevOps best practices. This gives vital information on the performance and health of a platform. In a distributed environment such as Kubernetes and microservices, it is even more true.

One of the great strengths of Kubernetes is the ability to scale your services and applications. When you reach thousand of applications, monitoring them manually or using scripts is not viable. You need to adopt a monitoring system that scales too! That's where Prometheus and Grafana come into the scene.

Prometheus will collect, store and allow you to leverage your platform metrics. On the other hand, Grafana will plug into Prometheus and allow you to create beautiful dashboards and charts.

Today, we'll go over what Prometheus is and the best way to deploy it on Kubernetes: using the operator. We'll see how to set up a monitoring platform with Prometheus and Grafana.

This tutorial will give you a good starting point with observability and go further!

## Time Series Analysis

<https://www.itl.nist.gov/div898/handbook/pmc/section4/pmc4.htm>

Time series data often arise when monitoring industrial processes or tracking corporate business metrics. The essential difference between modeling data via time series methods or using the process monitoring methods discussed earlier in this chapter is the following:

  Time series analysis accounts for the fact that data points taken over time may have an internal structure (such as autocorrelation, trend or seasonal variation) that should be accounted for.

This section will give a brief overview of some of the more widely used techniques in the rich and rapidly growing field of time series modeling and analysis.

Definition of Time Series: An ordered sequence of values of a variable at equally spaced time intervals.

Applications: The usage of time series models is twofold:

- Obtain an understanding of the underlying forces and structure that produced the observed data
- Fit a model and proceed to forecasting, monitoring or even feedback and feedforward control.

## Time Series Analysis is used for many applications such as

- Economic Forecasting
- Sales Forecasting
- Budgetary Analysis
- Stock Market Analysis
- Yield Projections
- Process and Quality Control
- Inventory Studies
- Workload Projections
- Utility Studies
- Census Analysis

## **[Monitoring](https://getbetterdevops.io/setup-prometheus-and-grafana-on-kubernetes/)**

Monitoring is a key pillar of DevOps best practices to ensure performance and health. In a distributed environment such as Kubernetes and microservices, it is even more true. This tutorial shows you how to build effectively a modern monitoring stack with Prometheus & Grafana on Kubernetes.

Prometheus will collect, store and allow you to leverage your platform metrics. On the other hand, Grafana will plug into Prometheus and allow you to create beautiful dashboards and charts.

**![Timeline](https://getbetterdevops.io/content/images/2022/09/image-71.png)**

**![Architecture](https://getbetterdevops.io/content/images/2022/09/image-73.png)**

The architecture diagram shows Prometheus is a multi-component monitoring system. The following pieces are integrated into the Prometheus deployment:

- Prometheus server scraping and stores time-series data.
- It also provides a user interface to query the metrics.
- Client libraries for instrumenting application code.
- Pushgateway supports metrics collection from short-lived jobs
- Exporters for services that do not instrument Prometheus metrics directly.
- Alertmanager handles real-time alerts based on triggers

## Metrics

<https://www.timescale.com/blog/four-types-prometheus-metrics-to-collect/>

Metrics measure performance, consumption, productivity, and many other software properties over time. They allow engineers to monitor the evolution of a series of measurements (like CPU or memory usage, request, duration, latencies, and so on) via alerts and dashboards. Metrics have a long history in the world of IT monitoring and are widely used by engineers together with logs and traces to detect when systems don’t perform as expected.

## What is **[OpenTelemetry](https://opentelemetry.io/docs/kubernetes/getting-started/)**?

A short explanation of what OpenTelemetry is, and is not.
OpenTelemetry is an Observability framework and toolkit designed to create and manage telemetry data such as traces, metrics, and logs. Crucially, OpenTelemetry is vendor- and tool-agnostic, meaning that it can be used with a broad variety of Observability backends, including open source tools like Jaeger and Prometheus, as well as commercial offerings. OpenTelemetry is a Cloud Native Computing Foundation (CNCF) project.

Overview
Kubernetes exposes a lot of important telemetry in many different ways. It has logs, events, metrics for many different objects, and the data generated by its workloads.

To collect all of this data we’ll use the OpenTelemetry Collector. The collector has many different tools at its disposal which allow it to efficiently collect all this data and enhance it in meaningful ways.

To collect all the data, we’ll need two installations of the collector, one as a Daemonset and one as a Deployment. The Daemonset installation of the collector will be used to collect telemetry emitted by services, logs, and metrics for nodes, pods, and containers. The deployment installation of the collector will be used to collect metrics for the cluster and events.

To install the collector, we’ll use the OpenTelemetry Collector Helm chart, which comes with a few configuration options that will make configure the collector easier. If you’re unfamiliar with Helm, check out the Helm project site. If you’re interested in using a Kubernetes operator, see OpenTelemetry Operator, but this guide will focus on the Helm chart.

## Statistics are used in the evaluation of metrics data points

I have made a short list of some of the statistics terms that were used in the Prometheus metric server documentation.

## What is a quartile?

**[Quartiles](https://www.statisticshowto.com/probability-and-statistics/statistics-definitions/what-are-quartiles/)** are also quantiles; they divide the distribution into four equal parts. Percentiles are quantiles that divide a distribution into 100 equal parts and deciles are quantiles that divide a distribution into 10 equal parts.

## WHAT IS A HISTOGRAM?

A frequency distribution shows how often each different value in a set of data occurs. A histogram is the most commonly used graph to show frequency distributions. It looks very much like a bar chart, but there are important differences between them.

**![Histogram](https://asq.org/-/media/Images/Learn-About-Quality/Histogram/histogram.png)**

## WHEN TO USE A HISTOGRAM

Use a histogram when:

- The data are numerical
- You want to see the shape of the data’s distribution, especially when determining whether the output of a process is distributed approximately normally

## exposition-format

```exposition-format

# HELP http_requests_total The total number of HTTP requests.
# TYPE http_requests_total counter
http_requests_total{method="post",code="200"} 1027 1395066363000
http_requests_total{method="post",code="400"}    3 1395066363000

# Escaping in label values:
msdos_file_access_time_seconds{path="C:\\DIR\\FILE.TXT",error="Cannot find file:\n\"FILE.TXT\""} 1.458255915e9

# Minimalistic line:
metric_without_timestamp_and_labels 12.47

# A weird metric from before the epoch:
something_weird{problem="division by zero"} +Inf -3982045

# A histogram, which has a pretty complex representation in the text format:
# HELP http_request_duration_seconds A histogram of the request duration.
# TYPE http_request_duration_seconds histogram
http_request_duration_seconds_bucket{le="0.05"} 24054
http_request_duration_seconds_bucket{le="0.1"} 33444
http_request_duration_seconds_bucket{le="0.2"} 100392
http_request_duration_seconds_bucket{le="0.5"} 129389
http_request_duration_seconds_bucket{le="1"} 133988
http_request_duration_seconds_bucket{le="+Inf"} 144320
http_request_duration_seconds_sum 53423
http_request_duration_seconds_count 144320

# Finally a summary, which has a complex representation, too:
# HELP telemetry_requests_metrics_latency_microseconds A summary of the response latency.
# TYPE telemetry_requests_metrics_latency_microseconds summary
telemetry_requests_metrics_latency_microseconds{quantile="0.01"} 3102
telemetry_requests_metrics_latency_microseconds{quantile="0.05"} 3272
telemetry_requests_metrics_latency_microseconds{quantile="0.5"} 4773
telemetry_requests_metrics_latency_microseconds{quantile="0.9"} 9001
telemetry_requests_metrics_latency_microseconds{quantile="0.99"} 76656
telemetry_requests_metrics_latency_microseconds_sum 1.7560473e+07
telemetry_requests_metrics_latency_microseconds_count 2693

```

The PromQL query below calculates the average requests per second over the last five minutes:

```exposition-format
rate(http_requests_total{api="add_product"}[5m])
```

To calculate the absolute change over a time period, we would use a delta function which in PromQL is called increase():

increase(http_requests_total{api="add_product"}[5m])

This would return the total number of requests made in the last five minutes, and it would be the same as multiplying the per second rate by the number of seconds in the interval (five minutes in our case):

rate(http_requests_total{api="add_product"}[5m]) *5* 60

Below is an example of how to create and increase a counter metric using the Prometheus client library for Python:

```python
from prometheus_client import Counter
api_requests_counter = Counter(
                        'http_requests_total',
                        'Total number of http api requests',
                        ['api']
                       )
api_requests_counter.labels(api='add_product').inc()
 
```

Gauges
Gauge metrics are used for measurements that can arbitrarily increase or decrease. This is the metric type you are likely more familiar with since the actual value with no additional processing is meaningful and they are often used. For example, metrics to measure temperature, CPU, and memory usage, or the size of a queue are gauges.

For example, to measure the memory usage in a host, we could use a gauge metric like:

```exposition-format
# HELP node_memory_used_bytes Total memory used in the node in bytes
# TYPE node_memory_used_bytes gauge
node_memory_used_bytes{hostname="host1.domain.com"} 943348382
```

The metric above indicates that the memory used in node host1.domain.com at the time of the measurement is around 900 megabytes. The value of the metric is meaningful without any additional calculation because it tells us how much memory is being consumed on that node.

Unlike when using counters, rate and delta functions don’t make sense with gauges. However, functions that compute the average, maximum, minimum, or percentiles for a specific series are often used with gauges. In Prometheus, the names of those functions are avg_over_time, max_over_time, min_over_time, and quantile_over_time. To compute the average of memory used on host1.domain.com in the last ten minutes, you could do this:

```exposition-format
avg_over_time(node_memory_used_bytes{hostname="host1.domain.com"}[10m])
```

## What is **[OpenStack](https://www.openstack.org)**

OpenStack: Open Source Cloud Computing Infrastructure

OpenStack is an open source cloud computing infrastructure software project and is one of the three most active open source projects in the world.

OpenStack is a free, open standard cloud computing platform. It is mostly deployed as infrastructure-as-a-service in both public and private clouds where virtual servers and other resources are made available to users. **[Wikipedia](https://en.wikipedia.org/wiki/OpenStack)**

Like **[Nutanix: Transform Your Business with Hybrid Multicloud](https://www.nutanix.com/)** it works in a multi-node environment to provision hardware resources.

There is a web UI but there is also a command line interface.

**[Getting Started](https://microstack.run/#get-started)**

```bash
# Install Multipass
sudo snap install multipass
# Get a fresh VM with Ubuntu 22.04 LTS
multipass launch --name microstack --cpus 4 --memory 16G --disk 50G && multipass shell microstack
# Install MicroStack
sudo snap install openstack
# Prepare a machine
sunbeam prepare-node-script | bash -x && newgrp snap_daemon
# Bootstrap OpenStack
sunbeam cluster bootstrap --accept-defaults
# Configure OpenStack
sunbeam configure --accept-defaults --openrc demo-openrc
# Launch a cloud instance
sunbeam launch ubuntu -n test
```
