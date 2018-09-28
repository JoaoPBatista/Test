---
summary: Applications secured with authentication request end-users to enter their credentials before using the applications. To allow new end-users to use your applications, OutSystems provides the Users application.
tags: support-Security; support-Security-featured
---

# Create an End-User and Grant Roles

Applications secured with authentication request end-users to enter their
credentials before using the applications. To allow new end-users to use your
applications, OutSystems provides the Users application.

Add new end-users as follows:

1. In your browser, navigate to  _http_ _:// < yourserver >/Users _ (for example, [ http://example.com/Users ](http://example.com/Users "http://example.com/Users") ); 
2. In the Users tab, create the new user; 
3. On the edit screen of the new user, grant permissions by assigning roles. 

## Example

Mary Jones is a new employee in the company and needs to have access to the
GoOutWeb application. This application is for finding, reviewing, and rating
places. Mary Jones will be the responsible for managing the end-users.

We’ve got to create a user for Mary Jones and allow her to have access to the
application and the report confirmation feature:

1. Open the Users application; 
2. In the Users tab, create a user for Mary Jones; 
3. Grant the following roles to her: 
  * `GoOutWebUser`: to access the GoOutWeb application; 
  * `UserManager`: to manage the end-users of the application. 
4. Test the application with Mary Jones.

