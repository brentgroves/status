# Week 49

## Father's direction

I love you my son and am enjoying spending time with you each and every day. I will always be there for you so please don't get so wrapped up in what you are doing to not seek my direction.  I am there to help you but I can't help you if you don't take time for me.  I have a plan for you and me today and as long as you look to me throughout the day we will have much joy and peace in our work my son.

## Notes

Notes from this meeting will be located at: ~/src/repsys/status/2023/week49.md
It can be viewed by logging into devcon2 as bcieslik,bcook,sjackson,cstangland,jdavis,or kyoung with password k8sAdmin1! and opening week49.md from visual studio code and pressing shift-ctrl-v
To get a fresh copy please run ~/freshstart.sh at a command prompt.

## A self join **[example](../../volumes/sql/examples/mssql/self_join.md)**


## **[Backup and Restore a Prometheus](https://devopstales.github.io/kubernetes/backup-and-retore-prometheus/)**

## **[Time Series Analysis](../../linux/time-series-analysis/time-series-analysis.md)**

Time series data often arise when monitoring industrial processes or tracking corporate business metrics. The essential difference between modeling data via time series methods or using the process monitoring methods discussed earlier in this chapter is the following:

Time series analysis accounts for the fact that data points taken over time may have an internal structure (such as autocorrelation, trend or seasonal variation) that should be accounted for.

Average **[example](../../linux/time-series-analysis/smoothing-techniques.md)**

Possible Usages:

- Tool life
- Cycle Time

Data collection techniques for time series analysis:

- Scraping using Prometheus
- Application directly inserts data into database.

## Gage Report

- **[review data sources](../../volumes/sql/gages/review_data_sources.sql)**
- **[create final key set](../../volumes/sql/gages/final_key_set.sql)**

## Create HTTP server metric

<https://prometheus.io/docs/tutorials/instrumenting_http_server_in_go/>
**[go-server-metrics](../../volumes/go/tutorials/prometheus/counter/go-server-metrics.md#test)**

## Create Grafina graph to visualize the metric

<https://prometheus.io/docs/tutorials/visualizing_metrics_using_grafana/>

## **[Prometheus Histograms](../../linux/prometheus/histograms/histograms.md)**

<https://andykuszyk.github.io/2020-07-24-prometheus-histograms.html>

## Use grafana with a **[mysql](https://www.techrepublic.com/article/how-to-connect-grafana-to-a-remote-mysql-database/)** data source

## Grafana Prometheus **[tutorial](https://youtu.be/EGgtJUjky8w)**

![dashboard](../../linux/grafana/dashboard.png)

## **[Grafana vs Power BI](https://www.metricfire.com/blog/grafana-vs-power-bi/)**

Grafana vs. Power BI – This is often a confusing decision for people wanting to select a data visualization and analytics tool with visually appealing and interactive insights. In this article, we highlight the features and benefits of both tools —Grafana and Power BI, bringing out their key differences to help you make a better decision.

Key Takeaways

- Grafana is adaptable for monitoring data from other application monitoring tools and offers scalability and affordability.
- Power BI is great for analyzing data from various sources but is more focused on business intelligence.
- Grafana is ideal for metric consolidation and monitoring, making it an affordable and easy-to-maintain solution for various data sources.
- Power BI is well-suited for business analytics, but it has limitations regarding data source integration and is primarily focused on business intelligence.

## Comparing next record to previous record

<https://www.scaler.com/topics/lag-function-in-sql/#:~:text=In%20SQL%20Server%20(Transact%2DSQL,making%20it%20easier%20to%20compare>.

In SQL Server (Transact-SQL), LAG() is a window function that allows us to compare the current record value with the value of previous records. This previous record value can be returned on the same record without the use of self-join, thus making it easier to compare.
