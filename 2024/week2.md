# The Father's direction

My son be content with the work I have given you to do. Do not be anxious or afraid about how the work turns out.  Trust me for the results.  I will decide what is best for you all that you need to do is try your best, listen to my directions, and then leave the results to me my son.

Don't worry about what you can not get to work just do your best. Be thankful for what I have given you to work on and trust me for the results.  Wait patiently and keep at it until I tell you to stop. Don't worry about what won't work because I am in control of that. Trust me my son.

Please trust me my son and do not be afraid.  I have a plan for you and those around you.  This plan will help you and sometimes be painful but you can endure the hardships you must faith because I will help you.  Remember I am responsible for everything you know and every thing you achieve.  If I want you to be able to resolve something then it will be.  If it is better for you not to be able to do something I will prevent it from happening.  What is important is that you listen to me throughout the day and do what I direct you to do and leave the results in my hand.  Trust me for all of your needs, peace, and happiness my son.

## Next

https://docs.konghq.com/kubernetes-ingress-controller/1.1.x/references/annotations/#konghqcomsnis

**[kong_oidc_example](../../research/api_management/api_gateway/kong/example/kong_oidc_example.md)**
<https://www.hcl-software.com/blog/versionvault/how-to-configure-microsoft-azure-active-directory-as-keycloak-identity-provider-to-enable-single-sign-on-for-hcl-compass>

<https://callistaenterprise.se/blogg/teknik/2023/04/20/kong-api-gateway-part1/>

## Linamar tenant

- Test login and OpenID Connect web app registration with User.Read.All scope for repsys.

## Active Directory B2C

<https://learn.microsoft.com/en-us/azure/active-directory-b2c/overview>

Azure Active Directory B2C provides business-to-customer identity as a service.
Your customers can use their preferred social, enterprise, or local account identities to get single sign-on access to your applications and APIs.

- New customizable User Flows such as signup and signin.
- New portal with new user interface
- Features isolated people groups as described in newer identity platform documents, ie. b2b,b2e, and b2c.  
- New entity type, Active Directory B2C, with new capabilities such as various signin user flows with the new GUI.

## **[OpenID](https://konghq.com/blog/engineering/openid-vs-oauth-what-is-the-difference)** Authentication

OpenID is an open standard that enables decentralized digital identity, allowing users to log into different websites using the same identity provider. For example, there are SSO options where you can use your Google or Facebook account to sign in to various sites across the web, without needing to create new usernames and passwords for each one. 

## **[OAuth2](https://auth0.com/intro-to-iam/what-is-oauth-2#:~:text=OAuth%202.0%2C%20which%20stands%20for,industry%20standard%20for%20online%20authorization.)** Authorization

OAuth 2.0, which stands for “Open Authorization”, is a standard designed to allow a website or application to access resources hosted by other web apps on behalf of a user. It replaced OAuth 1.0 in 2012 and is now the de facto industry standard for online authorization.

## **[OpenID Connect](https://konghq.com/blog/engineering/openid-vs-oauth-what-is-the-difference)** (OIDC): The Best of Both Worlds

OpenID Connect is an authentication protocol that extends OAuth 2.0 and can be utilized for sign-on purposes. It facilitates the verification of user identity by clients through an authorization server. OpenID Connect combines elements from both OpenID and OAuth:

It employs OAuth 2.0 flows for the authentication request and response enabling a seamless single sign-on experience similar to OpenID. Additionally, it incorporates an OAuth 2.0 token that allows clients to access APIs and retrieve user information.

Consequently, OpenID Connect offers both identity verification and delegated authorization capabilities enabling clients to securely access user data. By augmenting OAuth 2.0 with an identity layer featuring user profile claims OpenID Connect provides a means of achieving single sign-on functionality on top of the authorization framework offered by OAuth.

## **[API gateways](https://callistaenterprise.se/blogg/teknik/2023/04/20/kong-api-gateway-part1/)**

API gateways are becoming increasingly more popular, and for good reasons. As the number of APIs within an organisation grows, the amount of “plumbing” required to expose the APIs in a secure, efficient and maintainable way quickly becomes overwhelming. An API Gateway is an architectural pattern which introduces a transparent placeholder between API clients and the APIs, where Cross Cutting Concerns such as Access Control, Monitoring, Logging, Caching and Rate Limiting can be implemented.

**[Keycloak](https://en.wikipedia.org/wiki/Keycloak)** is an open source software product to allow single sign-on with identity and access management aimed at modern applications and services. As of March 2018 this WildFly community project is under the stewardship of Red Hat who use it as the upstream project for their Red Hat Single Sign-On product.

**[Relying Party](https://openid.net/developers/how-connect-works/)** (RP). RP stands for Relying Party, an application or website that outsources its user authentication function to an IDP.

Keycloak can be configured to rely on **[Microsoft's identity provider](https://www.hcl-software.com/blog/versionvault/how-to-configure-microsoft-azure-active-directory-as-keycloak-identity-provider-to-enable-single-sign-on-for-hcl-compass)**.



## Horizontal vs Vertical scaling

- Vertical scaling: Increase the capability of a single machine.
- Horizontal scaling: Add more nodes to share the workload.

## Microservices

- Divide API functionality into logical sub-groups.
- How to handle authentication/authorization given large number of microservices.
- API Gateway provides a centralized authentication/authorization, throttling, and loadbalancing for all microservices.
- Combine K8s Ingress Controller with an API Gateway features with many API Gateway products including the most prevalant Kong.

## Storage Solution

Provide both replication and horizontal scaling with any of several distributed storage clusters such as:

- Minio S3 compatible object storage
- Ceph is a free and open-source software-defined storage platform that provides object storage, block storage, and file storage built on a common distributed cluster foundation.

## API gateways

<https://callistaenterprise.se/blogg/teknik/2023/04/20/kong-api-gateway-part1/>

API gateways are becoming increasingly more popular, and for good reasons. As the number of APIs within an organisation grows, the amount of “plumbing” required to expose the APIs in a secure, efficient and maintainable way quickly becomes overwhelming. An API Gateway is an architectural pattern which introduces a transparent placeholder between API clients and the APIs, where Cross Cutting Concerns such as Access Control, Monitoring, Logging, Caching and Rate Limiting can be implemented.

Our API gateway will rely on a relying party, e.g. Microsoft's Identity Platform, for authentication and some authorization.

**[Relying Party](https://openid.net/developers/how-connect-works/)** (RP). RP stands for Relying Party, an application or website that outsources its user authentication function to an IDP.

Use **[Keycloak](https://www.keycloak.org/)** OAuth 2.0/OIDC server so not tied to any particular cloud specifice identity provider.

Configure **[Keycloak OS OIDC server with Microsoft's identity provider](https://www.hcl-software.com/blog/versionvault/how-to-configure-microsoft-azure-active-directory-as-keycloak-identity-provider-to-enable-single-sign-on-for-hcl-compass)**.
