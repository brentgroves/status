# Week48

## Fathers Will

I love you my son and look forward to the time we get to spend together today.  Entrust yourself to me and no one else and I will give you peace and happiness in whatever you are doing.  Remember the abilities and gifts you have been given are all from me as well as your trials and hardships.  I am in control of every situation you face so do not fear because I love you like no other.  Even your troubles have a purpose for good and no matter what you are doing you will have joy as long as you stay close to me and try your best :-)

## Metrics

<https://www.timescale.com/blog/four-types-prometheus-metrics-to-collect/>

Metrics measure performance, consumption, productivity, and many other software properties over time. They allow engineers to monitor the evolution of a series of measurements (like CPU or memory usage, request, duration, latencies, and so on) via alerts and dashboards. Metrics have a long history in the world of IT monitoring and are widely used by engineers together with logs and traces to detect when systems don’t perform as expected.

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

rate(http_requests_total{api="add_product"}[5m]) * 5 * 60

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

