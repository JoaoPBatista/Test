---
summary: To edit or create a theme you need to know the basics about the theme structure. This document shows how themes integrate into the platform through predefined blocks and placeholders.
tags: support-application_development; support-Front_end_Development
---

# Themes

A theme contains the details for visual presentation of your application. Changing a theme changes how your application looks. A theme can be applied to an entire application or to a UI Flow.

The default OutSystems themes are an integral part of from OutSystems Mobile UI Framework and OutSystems Web UI Framework. The frameworks enable quick development and implementation of best practices. Both frameworks have many  patterns, such as Carousel, ChatMessage, AnimatedLabel, Wizard, Columns4 and many more. The themes work well with the scaffolding, so you can quickly create CRUD interfaces, insert screens by dragging entities to UI Flows and use other accelerators. The UI frameworks are optimized for performance, which is particularly important in mobile development.

New applications inherit some of the CSS from the base theme. The easiest way to edit the theme theme is to generate new CSS by visiting  [Theme Customizer](<https://silkui.outsystems.com/silkuimobilecustomizer/>).

![](images/web-theme-example-1.png)

# The structure of a theme

The themes in the Silk framework follow a structure which is based on the platform screen requirements. Each theme has a list of blocks (for example, a header block) and each block consists of one or more placeholders (header title, header search...).

What follows is a simplified graph showing how a new theme inherits the layout from the base theme, and how the platform uses the blocks and placeholders to generate a page. The main layout has placeholders whose content are blocks (the Header placeholder will be replaced by the content generated in the Header block). The CSS is also inherited from the base theme, but can be overridden by the application CSS.

![](images/themes-concept.png)

## Blocks

Different types of the screen will require different blocks to function correctly within the platform. Here is the table which specifies the required blocks for screens in web applications:

<table markdown="1">
<thead>
<tr>
<th rowspan="2">
Type of Screen
</th>
<th colspan="7">
Web Block
</th>
</tr>
<tr>
<th>
Layout
</th>
<th>
Info Balloon
</th>
<th>
Pop-up Editor
</th>
<th>
Email
</th>
<th>
Header
</th>
<th>
Menu
</th>
<th>
Footer
</th>
</tr>
</thead>
<tbody>
<tr>
<th>
Blank Screen
</th>
<td>
Required
</td>
<td></td>
<td></td>
<td></td>
<td>
Required
</td>
<td>
Required
</td>
<td>
Required
</td>
</tr>
<tr>
<th>
List Screen
</th>
<td>
Required
</td>
<td></td>
<td></td>
<td></td>
<td>
Required
</td>
<td>
Required
</td>
<td>
Required
</td>
</tr>
<tr>
<th>
Show Screen
</th>
<td>
Required
</td>
<td></td>
<td></td>
<td></td>
<td>
Required
</td>
<td>
Required
</td>
<td>
Required
</td>
</tr>
<tr>
<th>
Edit Screen
</th>
<td>
Required
</td>
<td></td>
<td></td>
<td></td>
<td>
Required
</td>
<td>
Required
</td>
<td>
Required
</td>
</tr>
<tr>
<th>
Info Balloon
</th>
<td></td>
<td>
Required
</td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<th>
Pop-up Editor
</th>
<td></td>
<td></td>
<td>
Required
</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<th>
Email
</th>
<td></td>
<td></td>
<td></td>
<td>
Required
</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

The table can be interpreted like this:

* When creating or editing a blank screen in a web application, there should be web blocks for the layout, header, menu and footer, or:
* When creating or editing an Email web application, there is only one block required.

The main content of the screens is placed in the block named **Layout**. Depending on the platform for which the theme is developed, the layout can consist of different placeholders. For example, the layout in web application must have a placeholder that will show content (MainContent), but the breadcrumbs placeholder is optional.

This is the list of reserved names for the **Layout**  placeholders in the web themes.

* Title
* MainContent
* Breadcrumbs
* Actions
* Header
* Menu
* Footer

A mobile theme can have these placeholders in the layout block:

* HeaderLeft
* Title
* HeaderRight
* HeaderContent
* Content
* Bottom

The mobile themes have the block-specific events and actions, which are later compiled into JavaScript/React event listeners and functions. Do not delete default events and actions relevant for the screen purpose. 

## Placeholders

What placeholders to use depends on the type of screen. Here is an overview for the web applications:

<table markdown="1">
<thead>
<tr>
    <th>Type of Screen / Placeholder</th>
    <th>Title</th>
    <th>MainContent</th>
    <th>Actions</th>
    <th>Header</th>
    <th>Menu</th>
    <th>Footer</th>
</tr>
</thead>
<tbody>
<tr>
<th>Blank Screen</th>
<td></td>
<td>Required</td>
<td></td>
<td>Optional</td>
<td>Optional</td>
<td>Optional</td>
</tr>
<tr>
<th>List Screen</th>
<td>Required</td>
<td>Required</td>
<td>Optional</td>
<td>Optional</td>
<td>Optional</td>
<td>Optional</td>
</tr>
<tr>
<th>Edit Screen</th>
<td>Required</td>
<td>Required</td>
<td>Optional</td>
<td>Optional</td>
<td>Optional</td>
<td>Optional</td>
</tr>
<tr>
<th>Info Balloon</th>
<td></td>
<td>Required</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<th>Pop-up Editor</th>
<td></td>
<td>Required</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr>
<th>Email</th>
<td>Optional</td>
<td>Required</td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

Some examples:

* If, in the theme properties, a web application has a web block assigned for Blank Screen, the only required placeholder for that web block is MainContent, or:
* If, in the theme properties, a web application has a web block assigned for Email, the only required placeholder for that web block is Title, while MainContent is optional.

Menu items in web can be created automatically by drag and drop. If you want to keep the same functionality in your themes, create a menu web block with the required input parameters and the entities. Refer to the existing themes for input parameters and entities.

Here is an example of blocks for a web theme and their placeholders:

![](images/theme-layout.png)


# Creating a theme from a base theme

When you create a new app it already contains a copy of the CSS which you can edit. You can create new, additional, themes manually.

1. In the **Interface** tab right-click **Themes** and select **Add Theme**.
1. Enter the name of your new theme.
1. Optionally, change the **Base Theme**. If you do not see the theme you want in the list, add a reference to it.
1. With your theme selected in the Properties Pane, click on **Style Sheet**.
1. Enter your styles in the first tab of the CSS editor. You cannot edit the the original theme, but you can create new styles with the same class names and override the original styles.
