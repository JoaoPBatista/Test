---
summary: Learn more about the two areas where modules can be executed and debugged.
---

# Public and Personal Areas

A web application module can be executed and debugged in two different areas: the Public Area or the Personal Area.

<div class="info" markdown="1">

Mobile apps are always published and debugged in the Public Area.

</div>

## The Public Area

The **Public Area** is a common area of the environment to where modules are published when using "1-Click Publish".

When a module is published to the environment it is stored in the Public Area, and all changes become public to other developers. For example, if you change a screen and publish the module, other developers working on that module will have to merge their work with your changes. Also, developers executing the application will start using the screen with your changes.

A module is updated in the Public Area through the "1-Click Publish" operation. This operation generates a new version of the module and stores it in the environment, allowing you to keep your module under version control. Any new version of a module becomes available to other developers working on the same module.


## The Personal Area

Each developer has an associated **Personal Area** which he can use to test web application module changes without compromising the developments made by other team members in the same module.

When a module is executed in the Personal Area, changes made to the module are not visible to other developers that are also developing the same module (except database modifications &#8212; see below). This allows a developer to test and debug his changes privately without affecting any other developers. For example, if you change a screen and run the module, none of the developers working on this module are affected by those changes.

The only exception to this isolation is database modifications. Since the database is shared between the two areas, changing database data or schema will affect all developers, both the ones using their Personal Area and the ones using the Public Area.

A module is updated in the Personal Area through the "Run and Debug in *[login_name]* Personal Area" operation available in the Debugger menu. Besides updating your application in your Personal Area, this command will also attach the debugger to both your Personal Area and the Public Area. This means that, from this moment on, you will be able to debug threads executing in both areas.


### Personal Area Limitations

* The Personal Area is only available for web applications;

* If you are using your Personal Area and you have exposed functionality to other modules, any changes to this exposed functionality will not have any effect on modules using it;

* If you are using your Personal Area and your module is referencing Web Screens from another module, the links to these screens will redirect to the Public Area;

* You will only be able to run a module in your Personal Area after publishing it for the first time;

* To ensure consistency between areas, changes to some elements require the module to be published to the Public Area, instead of the Personal Area. These elements are the following:

    * Entities;
    * Site Properties;
    * Session Variables;
    * Timers;
    * Roles;
    * Module references.

* The module must be single-tenant;

* Processes are only executed in the Public Area;

* Timers are only executed in the Public Area;

* Emails are only executed in the Public Area.

