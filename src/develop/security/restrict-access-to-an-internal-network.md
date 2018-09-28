---
tags: support-devOps; support-Security; support-Security-featured
---

# Restrict Access to an Internal Network

You can tighten the security of your applications, or part of them, by only
allowing the access to end-users who have authenticated themselves in an IP
belonging to an internal network.

You can restrict internal network access to the following elements:

* UI Flows of a Web application (restricts the access of the Web Screens within the Flow); 
* Exposed SOAP Web Services; 
* Exposed REST APIs. 

To restrict these elements to internal network access set its **Internal
Access Only** property to `Yes` .

##  Internal Network Configuration

If you have OutSystems installed on-premises, you can configure your Internal
Network in the Service Center management console of your OutSystems
environment, under Administration » Security » Network Security.

If you have OutSystems PaaS, you must contact OutSystems Technical Support to configure your Internal
Network.