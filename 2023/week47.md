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

Now that the load balancer and ingress controller are working collect metrics using prometheus and graph time-series data in graphina.

Server Comparison:

- UDP Server - Broadcast data to certain mac addresses.
- MQTT Server - Publish/Subscribe model.
- OPC Server - Polls for tag changes. Clients subscribe to data points.
- Metric Server - Polls key/value pairs of data sources at a set interval. Maintains a time-series database.

**[Kube-Prometheus-stack](https://medium.com/israeli-tech-radar/how-to-create-a-monitoring-stack-using-kube-prometheus-stack-part-1-eff8bf7ba9a9)**, also as Prometheus Operator, is a popular open-source project providing complete monitoring and alerting solutions for Kubernetes clusters. It combines tools and components to create a monitoring stack for Kubernetes environments.

**![Prometheus-Grafana](https://miro.medium.com/v2/resize:fit:720/format:webp/1*EPHj4qLIyooRFebYERN3dA.png)**

## Cloud Provisioning Software

This software manages and controls hypervisors, storage solutions, and container orchestrators using an API. It helps to automate:

- dynamic allocation of storage
- creation of virtual machines
- life-cycle of containers

## OpenStack (Cloud Provisioning)


**[OpenStack Development Guide](https://ubuntu.com/engage/openstack-deployment-guide)**

OpenStack is one of the most active open source projects in the world. It is an essential component of private cloud infrastructure for countless businesses, and over the last few years, it has evolved to become the de-facto standard for implementing cloud computing platforms.

## Why Support OpenStack?

- Setting up a Cloud Provisioning service is time consuming but if it becomes much easier to do then compition will increase and costs will decrease.
- Integration Hypervisor and Kubernetes container orchestrator services so the K8s API includes the ability to request resources directly from the hypervisor.

## **[OpenStack Components](https://www.openstack.org/software/project-navigator/openstack-components#openstack-services)**

OpenStack Services
An OpenStack deployment contains a number of components providing APIs to access infrastructure resources. This page lists the various services that can be deployed to provide such resources to cloud end users.

- **[Compute Services](https://www.openstack.org/software/releases/antelope/components/nova)**
- **[Containers Service](https://www.openstack.org/software/releases/antelope/components/zun)**
- **[Bare Metal Provisioning](https://www.openstack.org/software/releases/antelope/components/ironic)**
- **[Life Cycle Management](https://www.openstack.org/software/releases/antelope/components/cyborg)**


## Canonical **[K8s-native MicroStack](https://ubuntu.com/blog/k8s-native-microstack)**

OpenStack is no doubt a wonderful and successful piece of software. It allows you to create your own cloud infrastructure, and thanks to its open-source nature, it’s free to use for everyone. But as with many giant software projects, all that power comes with a challenge: it is reasonably complex to install and configure. A number of OpenStack distributions do exist that intend to make engineers’ life a lot easier, but those also tend to be more complex than a non-experienced user would like them to be.

To solve this problem once and for all, Canonical created a simplified and easy-to-install distribution of OpenStack called **[MicroStack](https://microstack.run/).

### MicroStack References

<https://ubuntu.com/blog/k8s-native-microstack>

## Dell PowerEdge R620 Server

There are many discarded R620 that can be used to experiment with creating a multi-node MicroStack.

### R620 References

<https://savemyserver.com/dell-poweredge-r620-tech-specs/>

## Dell PowerEdge R620 Server Data Sheet

PowerEdge R620 Server - At A Glance
Manufacturer Dell
Brand PowerEdge
Model R620
Processors 2x Intel Xeon processor E5-2600 and E5-2600 v2 product families
Storage
Drive bay options:
 Up to 4 x 2.5” or
 Up to 8 x 2.5” or
 Up to 10 x 2.5” or
 Up to 4 x 2.5” + 2 x Express
Flash

Generation 12th Gen Server
Form Factor 1U Rack-Mountable

## React Native

https://www.lexis.solutions/blog/wrap-react-website-in-a-native-app

React and React Native are the most popular technologies for developing web and mobile applications right now. They are widely adopted by developers and companies alike due to their efficiency, speed, and ability to create high-performance user interfaces.

React Native is a popular choice when it comes to developing hybrid apps. It's an open-source framework created by Facebook that combines the benefits of both React and React Native. It enables developers to build high-performance applications compatible with multiple platforms while providing access to device-specific features like push notifications.

