# Week 47

## My Father's will

I love you my son.  Please don't forget that I am always with you.  Through the tough times I will support you.  Every moment while you work I am with you too.  I intend for you and I to have an enjoyable time together as my plan unfolds for you life.  Remember to help and give your all to everyone I place in your life and you will have peace and joy in abundance my beloved son!

Good morning dear ones,

This status report will be available soon from your devcon2 logon at ~/src/repsys/status/2023/week47.md and you can view it by running Visual Studio Code from devcon2 and adding the ~/src/repsys folder to your workspace.  Until the automation process to update these files is complete please open a terminal and run ~/freshstart.md before viewing the status report or ~/src/repsys/README.md which is the index of the report system project.

Host: devcon2
IP: 10.1.0.120
bcieslik,bcook,sjackson,cstangland,jdavis,kyoung/k8sAdmin1!

## Time Off report query

While working on this query with Kevin took some notes on the query process that I use hoping it will be helpful to others.

- **[Query Making by Example](../../volumes/sql/query_making/query-making-by-example.md)**

## Report System on Private Cloud

### Observability

Now that the load balancer and ingress controller are working try getting the ingress controller to collect metrics using prometheus and graph data in graphina.

- Install MicroK8s observability stack
- monitor the ingress controller with prometheus
- configure MicroK8s to ship logs and metric data to an external
 Observability stack for logging, monitoring and alerting.

The Observability stack used in this example consists of:
Prometheus
Elasticsearch
Alertmanager

## What is OpenStack?

OpenStack is a collection of open-source projects designed to work together to form the basis of a cloud. OpenStack can be used for both private and public cloud implementation.

## Canonical MicroStack

OpenStack is no doubt a wonderful and successful piece of software. It allows you to create your own cloud infrastructure, and thanks to its open-source nature, it’s free to use for everyone. But as with many giant software projects, all that power comes with a challenge: it is reasonably complex to install and configure. A number of OpenStack distributions do exist that intend to make engineers’ life a lot easier, but those also tend to be more complex than a non-experienced user would like them to be.

To solve this problem once and for all, Canonical created a simplified and easy-to-install distribution of OpenStack called **[MicroStack](https://microstack.run/).

### MicroStack References

<https://ubuntu.com/blog/k8s-native-microstack>

## Dell PowerEdge R620 Server

There are many discarded R620 that can be used to experiment with MicroStack.

### R620 References

https://savemyserver.com/dell-poweredge-r620-tech-specs/

## Dell PowerEdge R620 Server Data Sheet

PowerEdge R620 Server - At A Glance
Manufacturer	Dell
Brand	PowerEdge
Model	R620
Processors	2x Intel Xeon processor E5-2600 and E5-2600 v2 product families
Storage	
Drive bay options:
 Up to 4 x 2.5” or
 Up to 8 x 2.5” or
 Up to 10 x 2.5” or
 Up to 4 x 2.5” + 2 x Express
Flash

Generation	12th Gen Server
Form Factor	1U Rack-Mountable

