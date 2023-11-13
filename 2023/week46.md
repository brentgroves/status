# My Father's will

I love you my son.  Please don't forget that I am always with you.  Through the tough times I will support you.  Every moment while you work I am with you too.  I intend for you and to have an enjoyable time together as my plan unfolds for you life.  Remember to help and give your all to everyone I place in your life and you will have peace and joy in abundance my beloved son!

Good morning dear ones,
I hope everyone is more or less adjusted to the time change by now :-/ If you are not you are in good company I'm sure.  As always please feel to contact me at home or work about anything you need!

This status report will be available soon from your devcon2 logon at ~/src/repsys/status/2023/week46.md and you can view it by running Visual Studio Code and adding the ~/src/repsys folder to your workspace.

bcook,sjackson,kyoung/k8sAdmin1!

## Observability

Now that the load balancer and ingress controller are working try getting the ingress controller to collect metrics using prometheus and graph data in graphina.

- Install MicroK8s observability stack
- monitor the ingress controller with prometheus
- configure MicroK8s to ship logs and metric data to an external
 Observability stack for logging, monitoring and alerting.

The Observability stack used in this example consists of:
Prometheus
Elasticsearch
Alertmanager

