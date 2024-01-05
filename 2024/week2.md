# The Father's direction

My son be content with the work I have given you to do. Do not be anxious or afraid about how the work turns out.  Trust me for the results.  I will decide what is best for you all that you need to do is try your best, listen to my directions, and then leave the results to me my son.

Don't worry about what you can not get to work just do your best. Be thankful for what I have given you to work on and trust me for the results.  Wait patiently and keep at it until I tell you to stop. Don't worry about what won't work because I am in control of that. Trust me my son.

Please trust me my son and do not be afraid.  I have a plan for you and those around you.  This plan will help you and sometimes be painful but you can endure the hardships you must faith because I will help you.  Remember I am responsible for everything you know and every thing you achieve.  If I want you to be able to resolve something then it will be.  If it is better for you not to be able to do something I will prevent it from happening.  What is important is that you listen to me throughout the day and do what I direct you to do and leave the results in my hand.  Trust me for all of your needs, peace, and happiness my son.

## Next

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

## OpenID Connect

The best of both worlds. It combines the best of OpenID authentication with OAuth2 authorization features.

- supported by Azure, AWS, and Google identity platforms.

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
