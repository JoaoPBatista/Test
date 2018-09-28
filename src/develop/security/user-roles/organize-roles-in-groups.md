---
summary: Learn how to apply a set of roles to an end-user at once by using Groups.
tags: support-Security
---

# Organize Roles in Groups

The access of end-users to an application and its features is managed using
Roles. Some of these users can share the same set of roles for one or several
applications. You can assign roles to Groups to help you grant the same set of
roles to a set of users. This avoids the need to individually manage the
association between roles and users.

This is typically done as follows:

1. In your browser, navigate to _http://&lt;yourserver&gt;/Users_ (for example, [http://example.com/Users](http://example.com/Users "http://example.com/Users") ); 
2. In the Groups tab, create a new group; 
3. After creating the group, open it and add the related access roles; 
4. To assign the group to an end-user: 
    * In the group, add end-users to it using the  Members  section, or; 
    * Go to the  Users  tab, click on the end-user and assign the group. 

## Example

In the GoOutWeb application, an application to review and rate places, some
end-users need to have access to the application to manage the reviews and the
end-users. We’ve got to grant them two roles:

* `PlaceManager`: to add and edit places; 
* `UserManager`: to manage and block the users with reported reviews. 

We can group these two roles in a group called `ReviewManagers`:

1. Open the  Users  application; 
2. In the  Groups  tab, create a group called `ReviewManagers`; 
3. Add the roles `PlaceManager` and `UserManager` to the group; 
4. Assign the group to the end-users. 

In case you need to add new roles to the review managers group, you automatically grant those roles to all the members of the group.
