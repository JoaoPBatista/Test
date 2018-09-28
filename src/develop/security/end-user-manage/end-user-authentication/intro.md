---
summary: Learn about Internal, Active Directory and LDAP end-user authentication in OutSystems.
tags: support-Mobile_Apps; support-webapps
---

# End-User Authentication

When you start developing a new module it has the built-in logic for end-user authentication. OutSystems comes with three distinct authentication modes: Internal, Active Directory, and LDAP.

Internal
:  The default authentication mode. The end-user information is stored in the OutSystems database. The credentials are not stored, but a cryptographic hash function is computed using the credentials and only its result is stored. When the end-user attempts to logs in, the hash function is computed again and its result is compared with what is in the database.

Active Directory
:  Uses your Active Directory to authenticate the end-users.

LDAP
:  Authenticates the end-user against your LDAP server. At the moment OutSystems supports only the LDAP end-user authentication against Active Directory.

## Authentication flow

When the end-user uses the application for the first time and the accessed screen allows only authenticated end-users to see it, a security exception is raised. OutSystems will do the following: 

1. If the platform is [configured to use Windows Integrated Authentication](<integrated-authentication.md>) and the end-user is inside the [internal network](<../../restrict-access-to-an-internal-network.md>), the end-user is authenticated using Windows Integrated authentication. Once the end-user makes a request, the server replies with an HTTP 401 status, signaling to the end-user browser that authentication is required. If the browser already has the end-user credentials stored, it automatically sends the credentials to the web server. Otherwise, the browser displays a form for the end-user to input the credentials and sends them to the server. This means that even if you have a custom Login page, the end-user will not see it.

2. If the platform is not configured to use Windows Integrated Authentication, the end-user is redirected to a Login screen. When the end-user submits the credentials,
    1. The credentials are validated against the OutSystems database.
    2. If the platform is configured to authenticate using Active Directory, the credentials are validated against the configured domain server.
    3. If the platform is configured to authenticate using LDAP the credentials are validated against the Active Directory LDAP server configured. External LDAP is currently not supported for the end-user authentication.

3. If after this process the end-user could not be authenticated, then an "Invalid Login" message is displayed to the end-user.