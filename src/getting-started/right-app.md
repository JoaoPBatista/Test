---
summary: Learn what is the right app for your project. Know the difference between web and mobile apps in OutSystems and what to choose for your needs. 
tags: support-application_development; support-devOps; support-Infrastuture_Architecture; support-Mobile_Apps; support-webapps; support-Mobile_Apps-overview; support-webapps-overview
---

# Choose the Right App for Your Project

When creating a new app in OutSystems and according to your project's requirements, you need to select the type of application you want to develop. For each development scenario, different tools and features are available.

![](images/right-app-1.png?width=600)

## What is a Mobile App?

In OutSystems, a Mobile App is a native app shell, developed using Apache Cordova, that wraps a web app developed using the OutSystems visual language. The app has user experience that is mobile-optimized and can access the device's capabilities and features using plugins. It can work offline and have data-caching features thanks to access to the device's local storage. The developed code is cross-platform, this means that you only have to develop one project and the application works on all the supported mobile platforms (iOS and Android). You can generate application packages and distribute them in the stores or you can distribute them to a set of users.

![](images/mobile-vs-web.png)

## What is a Web App?

In OutSystems, a Web App is an application with a responsive interface that runs in the browser, displaying a user experience adapted to all kinds of devices and screen sizes. It is developed using the OutSystems visual language. You can interact with the device's features and capabilities by extending the application code using HTML5 and JavaScript. For it to work without an internet connection you must use a third-party component. It's not necessary for the user to install it on the device, the third-party component only needs the URL for it to open in the browser of the desktop, laptop, mobile device or any device with a browser. This type of app is mostly used for displaying a high volume of data, like dashboards and tables, and it's crucial when targeting web desktops and responsive apps.

![](images/mobile-vs-web-what-is-web.png)

## Comparison Between Mobile and Web Apps in OutSystems  

<table border="1" cellpadding="1" cellspacing="1" class="mt-responsive-table" style="border:none;">
    <thead>
        <tr>
            <th class="mt-bgcolor-ffffff" scope="col" style="border-bottom:1px solid #E7ECED;text-align:center;vertical-align:middle;">
            <p><span class="mt-font-size-20"><strong>Web</strong></span></p>

            <p><img alt="" class="internal default" height="125px" src="images/mobile-vs-web-web.png" style="width: 126px; height: 125px;" width="126px" /></p>
            </th>
            <th class="mt-bgcolor-ffffff" scope="col" style="border-bottom:1px solid #E7ECED;text-align:center;vertical-align:middle;"><span class="mt-font-size-20"><strong>vs</strong></span></th>
            <th class="mt-bgcolor-ffffff" scope="col" style="border-bottom:1px solid #E7ECED;text-align:center;">
            <p><span class="mt-font-size-20"><strong>Mobile</strong></span></p>

            <p><img alt="" class="internal default" height="125px" src="images/mobile-vs-web-mobile.png" style="width: 126px; height: 125px;" width="126px" /></p>
            </th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td class="mt-bgcolor-ffffff" data-th="Web" style="border:none;border-bottom:1px solid #E7ECED;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="56px" src="images/mobile-vs-web-code-reusability-web.png" style="width: 150px; height: 56px;" width="150px" /></p>

            <p>One codebase for all devices and screen sizes.</p>

            <p> </p>
            </td>
            <td class="mt-bgcolor-ffffff" data-th="vs" style="border:none;border-bottom:1px solid #E7ECED;text-align:center;vertical-align:middle;"><strong>Code Reusability</strong></td>
            <td class="mt-bgcolor-ffffff" data-th="Mobile" style="border:none;border-bottom:1px solid #E7ECED;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="56px" src="images/mobile-vs-web-code-reusability-mobile.png" style="width: 132px; height: 56px;" width="132px" /></p>

            <p>One codebase for all supported mobile platforms.</p>

            <p> </p>
            </td>
        </tr>
        <tr>
            <td data-th="Web" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="59px" src="images/mobile-vs-web-runs-in-web.png" style="width: 239px; height: 59px;" width="239px" /></p>

            <p>A browser.<br />
            No installation is needed.</p>

            <p> </p>
            </td>
            <td data-th="vs" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;vertical-align:middle;"><strong>Runs in</strong></td>
            <td data-th="Mobile" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="65px" src="images/mobile-vs-web-runs-in-mobile.png" style="width: 116px; height: 65px;" width="116px" /></p>

            <p>Mobile devices. Needs to be installed and is not supported in the browser.</p>

            <p> </p>
            </td>
        </tr>
        <tr>
            <td class="mt-bgcolor-ffffff" data-th="Web" style="border:none;border-bottom:1px solid #E7ECED;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="165px" src="images/mobile-vs-web-user-experience-web.png" style="width: 240px; height: 165px;" width="240px" /></p>

            <p>Responsive layout for all screen sizes and types.</p>

            <p> </p>
            </td>
            <td class="mt-bgcolor-ffffff" data-th="vs" style="border:none;border-bottom:1px solid #E7ECED;text-align:center;vertical-align:middle;"><strong>User Experience</strong></td>
            <td class="mt-bgcolor-ffffff" data-th="Mobile" style="border:none;border-bottom:1px solid #E7ECED;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" src="images/mobile-vs-web-user-experience-mobile.gif" /></p>

            <p>Dedicated mobile UI patterns and experiences, such as animations and screen transitions.</p>

            <p> </p>
            </td>
        </tr>
        <tr>
            <td data-th="Web" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="93px" src="images/mobile-vs-web-performance-web.png" style="width: 232px; height: 93px;" width="232px" /></p>

            <p>AJAX responsive patterns. Depends heavily on the internet connection.</p>

            <p> </p>
            </td>
            <td data-th="vs" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;vertical-align:middle;"><strong>Performance</strong></td>
            <td data-th="Mobile" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="93px" src="images/mobile-vs-web-performance-mobile.png" style="width: 164px; height: 93px;" width="164px" /></p>

            <p>Mobile-optimized performance. App logic can run on the device and the data exchange with the server is reduced.</p>

            <p> </p>
            </td>
        </tr>
        <tr>
            <td data-th="Web" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="94px" src="images/mobile-vs-web-access-device-web.png" style="width: 187px; height: 94px;" width="187px" /></p>

            <p>HTML5 supported device capabilities.</p>

            <p> </p>
            </td>
            <td data-th="vs" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;vertical-align:middle;">
            <p><strong>Access to Device <span style="line-height:inherit;">Capabilities</span></strong></p>
            </td>
            <td data-th="Mobile" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="96px" src="images/mobile-vs-web-access-device-mobile.png" style="width: 172px; height: 96px;" width="172px" /></p>

            <p>Access to full range of device capabilities (using Cordova plugins).</p>

            <p> </p>
            </td>
        </tr>
        <tr>
            <td data-th="Web" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="79px" src="images/mobile-vs-web-offline-web.png" style="width: 240px; height: 79px;" width="240px" /></p>

            <p>No default offline or standalone capabilities (possible to use third-party components).</p>

            <p> </p>
            </td>
            <td data-th="vs" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;vertical-align:middle;"><strong>Offline capabilities</strong></td>
            <td data-th="Mobile" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="81px" src="images/mobile-vs-web-offline-mobile.png" style="width: 180px; height: 81px;" width="180px" /></p>

            <p>Using local storage for storing offline data. Client logic running on the device.</p>

            <p> </p>
            </td>
        </tr>
        <tr>
            <td data-th="Web" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="68px" src="images/mobile-vs-web-deployments-web.png" style="width: 240px; height: 68px;" width="240px" /></p>

            <p>Automatic update on browser page refresh.</p>

            <p> </p>
            </td>
            <td data-th="vs" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;vertical-align:middle;"><strong>Deployments/Updates</strong></td>
            <td data-th="Mobile" style="border:none;border-bottom:1px solid #E7ECED;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="69px" src="images/mobile-vs-web-deployments-mobile.png" style="width: 143px; height: 69px;" width="143px" /></p>

            <p>Most updates are made automatically on screen change. New installation required only when changing the native shell.</p>

            <p> </p>
            </td>
        </tr>
        <tr>
            <td data-th="Web" style="border:none;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="100px" src="images/mobile-vs-web-distribution-web.png" style="width: 264px; height: 100px;" width="264px" /></p>

            <p>Share the app’s link with users.</p>

            <p> </p>
            </td>
            <td data-th="vs" style="border:none;background:#fff;text-align:center;vertical-align:middle;"><strong>Distribution</strong></td>
            <td data-th="Mobile" style="border:none;background:#fff;text-align:center;">
            <p> </p>

            <p><img alt="" class="internal default" height="98px" src="images/mobile-vs-web-distribution-mobile.png" style="width: 265px; height: 98px;" width="265px" /></p>

            <p>In-House or via Mobile app stores.</p>

            <p> </p>
            </td>
        </tr>
    </tbody>
</table>


<!-- Hopefully temporary workaround to force publishing images used in table above -->
<div style="display: none;" markdown="1">
![](images/mobile-vs-web-web.png)
![](images/mobile-vs-web-mobile.png)
![](images/mobile-vs-web-code-reusability-web.png)
![](images/mobile-vs-web-code-reusability-mobile.png)
![](images/mobile-vs-web-runs-in-web.png)
![](images/mobile-vs-web-runs-in-mobile.png)
![](images/mobile-vs-web-user-experience-web.png)
![](images/mobile-vs-web-user-experience-mobile.gif)
![](images/mobile-vs-web-performance-web.png)
![](images/mobile-vs-web-performance-mobile.png)
![](images/mobile-vs-web-access-device-web.png)
![](images/mobile-vs-web-access-device-mobile.png)
![](images/mobile-vs-web-offline-web.png)
![](images/mobile-vs-web-offline-mobile.png)
![](images/mobile-vs-web-deployments-web.png)
![](images/mobile-vs-web-deployments-mobile.png)
![](images/mobile-vs-web-distribution-web.png)
![](images/mobile-vs-web-distribution-mobile.png)
</div>


## What is a Service?

As your application grows, you can use [Services](../develop/reuse-and-refactor/services.md) to abstract specific core concepts and expose functionality to other applications, following a service-oriented architecture.
