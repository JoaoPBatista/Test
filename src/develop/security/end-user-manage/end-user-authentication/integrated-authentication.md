---
summary: Learn more about Integrated Windows Authentication in OutSystems.
tags: support-Mobile_Apps; support-webapps
---

# Integrated Authentication

OutSystems natively supports Integrated Windows Authentication so you can use a centralized management of the end-users and have automatic authentication in your applications. Integrated authentication allows the end-users to access applications using their domain credentials.

When the end-user tries to access a web screen that requires authentication, the application server returns an HTTP 401 status, signaling that the end-user is trying to access a resource that requires authentication. The browser then sends the credentials the end-user used to authenticate in the Windows operating system, or if unable to do so, prompts the end-user to provide the credentials. From then on, the browser automatically sends the credentials when they are required, without the end-user having to insert the domain credentials again.

## Elements that Support Integrated Authentication

Enable Integrated Authentication by setting the `Integrated Authentication` property in these elements to `Yes`. You can enable integrated authentication for all applications, or for the specific elements inside an application. What follows is the list of elements that support Integrated Authentication.

Web Screens
:    The end-users accessing it will have to be authenticated by Integrated Authentication.

Web Flows
:    All screens that don't have set the `Integrated Authentication` property inherit its value form the web flow.

Exposed and Consumed SOAP Web Services
:    While processing the request the OutSystems application always asks the web service client for its credentials. Depending on the client that invokes the SOAP Web Service, it may not be possible to send the credentials and to consume its services. If a consumed Web Service is invoked inside a web screen you are probably expecting that delegation can be used. But, there are some limitations. If your system is configured to use NTLM, delegation is not supported.

## Integrated Authentication Built-in Actions

OutSystems has built-in actions and functions that use Integrated Windows Authentication.

* [IntegratedSecurityGetDetails](<../../../../ref/apis/system-actions.md#IntegratedSecurityGetDetails>): Gets information about the current Windows user.
* [IntegratedSecurityCheckRole](<../../../../ref/apis/system-actions.md#IntegratedSecurityCheckRole>): Checks whether the current Windows user has access to a specific Windows role.


## Remarks

To use integrated authentication, both the client and front-end server must be in the same domain and must have an Active Directory that stores information about the end-users and their credentials.