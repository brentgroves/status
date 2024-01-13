# Father's will

Fear not my son.  I love you and am always with you.  It is me that controls every situation you face. Remember that every trouble that you go through is for your ultimate good. You must not stay as you are. There are things you must learn and the only way for that to happen is for you and I to face hardships together.  So do not fear when you face trials for this is necessary in order for you to grow into a kind and loving man full of hope in my love for you!

## week 3

## next

gage query
<https://gateway-api.sigs.k8s.io/guides/http-routing/>
<https://gateway-api.sigs.k8s.io/#whats-the-difference-between-gateway-api-and-an-api-gateway>

## Trial Balance

There was a bug in Plex.account_period_balance_recreate_period_range and Plex.account_period_balance_recreate_open_period_range having to do with a new account being added with debit and credit balances in December and January.

- changed mssql code first
- changing mysql code next
- review code change
- talk about SQL debugging in MSSQL, MySQL, and PostgreSQL

## Review Azure requirements

Plan was to ask for space on an Azure SQL Managed Instance, Power BI, single node AKS cluster, app registration, and access to an Azure DevOps repository to start.  Research using Azure Bastion to enable Microsoft Teams App to access K8s hosted UI and Postgres Cluster for reporting.

Getting very interested in what Bastion can do! If you think it is a good idea would you allow me to contact your Bastion guy?  If not I can just wait for the meeting you were talking about yesterday :-)

## What is a Bastion Host?

![](https://discover.strongdm.com/hs-fs/hubfs/Imported_Blog_Media/605d2e18679dad4a2e0b7df4_StrongDM-1-AWS-bastion-host-user-flow-3.jpg?width=780&height=438&name=605d2e18679dad4a2e0b7df4_StrongDM-1-AWS-bastion-host-user-flow-3.jpg)

A bastion host is a server used to manage access to an internal or private network from an external network - sometimes called a jump box or jump server. Because bastion hosts often sit on the Internet, they typically run a minimum amount of services in order to reduce their attack surface. They are also commonly used to proxy and log communications, such as SSH sessions.

<https://docs.oracle.com/en-us/iaas/Content/Bastion/Tasks/managingsessions.htm#managingsessions>

Oracle Bastion allows connection via Sock5 dynamic port forwarding session but Microsoft does not.

## What is Azure Bastion?

It might be a **[SOCKs5 proxy](https://securityintelligence.com/posts/socks-proxy-primer-what-is-socks5-and-why-should-you-use-it/)** is more secure because it establishes a full TCP connection with authentication and uses the Secure Shell (SSH) encrypted tunneling method to relay the traffic.

Is our Bastion host configured to provide SSH tunneling (Dynamic Port Forwarding) from an Azure Public IP to a VM or computer within our companies network, remote port forwarding, taking care of TLS termination?

![](https://learn.microsoft.com/en-us/azure/bastion/media/connect-ip-address/ip-address.png)

<https://docs.oracle.com/en-us/iaas/Content/Bastion/Tasks/managingsessions.htm#managingsessions>

## **[Azure Bastion Native Client Support](https://codyburkard.com/blog/bastionabuse/)**

Instead of logging in through the Azure Portal, Azure Bastion now allows users to connect using their native RDP or SSH clients.

If so I believe Bastion can be setup to route traffic to our K8s hosted API gateway which has it's own routing, throttling, TLS termination, and IAM authentication and authorization scheme.

If TLS termination is done by our Bastion host then we will probably need to pay for a Public IP and a TLS certificate. Once this is done I believe we will be able to access our data warehouse reporting UI and micro-services from a Microsoft Teams reporting app.

Azure Bastion is a fully managed PaaS service that you provision to securely connect to virtual machines via private IP address. It provides secure and seamless RDP/SSH connectivity to your virtual machines directly over TLS from the Azure portal, or via the native SSH or RDP client already installed on your local computer. When you connect via Azure Bastion, your virtual machines don't need a public IP address, agent, or special client software.

Bastion provides secure RDP and SSH connectivity to all of the VMs in the virtual network for which it's provisioned. Using Azure Bastion protects your virtual machines from exposing RDP/SSH ports to the outside world, while still providing secure access using RDP/SSH.

The following diagram shows connections to virtual machines via a Bastion deployment that uses a Basic or Standard SKU.

![](https://learn.microsoft.com/en-us/azure/bastion/media/bastion-overview/architecture.png)

## What is **[OpenStack](https://www.openstack.org/software/)**

OpenStack is a an open source cloud operating system managing compute, storage, and networking resources throughout a datacenter using APIs.

![](https://object-storage-ca-ymq-1.vexxhost.net/swift/v1/6e4619c416ff4bd19e1c087f27a43eea/www-images-prod/openstack-logo/2016R/OpenStack-Logo-Horizontal.SVG)
![](https://object-storage-ca-ymq-1.vexxhost.net/swift/v1/6e4619c416ff4bd19e1c087f27a43eea/www-assets-prod/learn/homepage-OpenStack-SFAs.svg)

![](https://docs.openstack.org/install-guide/_images/openstack_kilo_conceptual_arch.png)

**[OpenStack](https://en.wikipedia.org/wiki/OpenStack)** is a free, open standard cloud computing platform. It is mostly deployed as infrastructure-as-a-service in both public and private clouds where virtual servers and other resources are made available to users.

## Open Stack History

<https://docs.openstack.org/project-team-guide/introduction.html>

<https://fedscoop.com/agencies-open-up-to-openstack/>

Three out of four government IT professionals in a new poll say their agencies are now using cloud computing services. The new survey also found that a significant portion of the respondents have favorable perceptions about the cost, security and ease of deploying the popular open source software platform, OpenStack, for their on-premises cloud computing initiatives.

How Governments Use **[OpenStack](https://vexxhost.com/blog/how-governments-use-openstack-around-the-world/
)
Governments all over the world have important priorities. Keep their citizens safe, keep law and order within their jurisdiction, and problem solve any issues that arise are just some of the issues that they face on a day to day basis. Although the way that they govern their countries the following countries have one thing in common: OpenStack.

**The United States Of America**
In the United States, the National Security Agency (NSA) utilizes the power of OpenStack to keep abreast of the high-security needs of the country. The implementation of OpenStack at the governmental level was such a success that the NSA plan on implementing OpenStack to all 16 agencies that make up the intelligence community in the United States. Considering the emphasis that the United States place on security, it is evident that OpenStack delivers where it matters most.

Moreover, the role of OpenStack in government security for the United States is good for OpenStack users. Why? Because the NSA has such strong security requirements, it developed systems to accommodate these requirements. From securing APIs and guest OSes to developing code to suit their needs, the OpenStack community can experience the security benefits for themselves.
