# Week 49

## Father's direction

I love you my son and am enjoying spending time with you each and every day. I will always be there for you so please don't get so wrapped up in what you are doing to not seek my direction.  I am there to help you but I can't help you if you don't take time for me.  I have a plan for you and me today and as long as you look to me throughout the day we will have much joy and peace in our work my son.

## Notes

Notes from this meeting will be located at: ~/src/repsys/status/2023/week49.md
It can be viewed by logging into devcon2 as bcieslik,bcook,sjackson,cstangland,jdavis,or kyoung with password k8sAdmin1! and opening week49.md from visual studio code and pressing shift-ctrl-v
To get a fresh copy please run ~/freshstart.sh at a command prompt.

## **[Time Series Analysis](../../linux/time-series-analysis/time-series-analysis.md)**

Time series data often arise when monitoring industrial processes or tracking corporate business metrics. The essential difference between modeling data via time series methods or using the process monitoring methods discussed earlier in this chapter is the following:

Time series analysis accounts for the fact that data points taken over time may have an internal structure (such as autocorrelation, trend or seasonal variation) that should be accounted for.

Usages:

- Tool life

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

## Comparing next record to previous record

<https://www.scaler.com/topics/lag-function-in-sql/#:~:text=In%20SQL%20Server%20(Transact%2DSQL,making%20it%20easier%20to%20compare>.

In SQL Server (Transact-SQL), LAG() is a window function that allows us to compare the current record value with the value of previous records. This previous record value can be returned on the same record without the use of self-join, thus making it easier to compare.
