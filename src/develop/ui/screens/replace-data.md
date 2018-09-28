---
summary: Replace data in template based screens with your own data. The replacement can be manual or semi-automatic.
---

# Replace the sample data in template based screens

You can replace [sample data](<sample-data.md>) either manually or semi-automatically, in a screen created from a [Screen Template](<screen-templates.md>). The manual replacement involves editing the data sources and updating the user interface elements accordingly, and can be assisted by the semi-automated replacement.

## Manual replacement of sample data

Use the manual replacement when you want full control over the changes in the screen. Here are some examples of the manual replacement steps.

1. Remove the UI elements that you don't need. This minimizes the number of warnings in the later steps.
2. Delete the sample data references. In the element tree, locate the screen you want to edit. Remove the source of the data: in a web application, open the aggregates inside the **Preparation** action and delete the source entries inside the aggregates; in a mobile app, delete the source entries inside the aggregates assigned to the screen.
3. Insert the entries for new sources.
4. Replace the data references.
5. Review the errors and warnings in the **TrueChange** pane. Double-click on each error and warning, and fix it by assigning a valid variable or by deleting the associated widget.

## Semi-automatic replacement of sample data

The semi-automatic replacement works by dragging and dropping an entity to the widget that supports the automatic data replacement. In some instances the labels associated with the data in your screen are also replaced. The semi-automatic replacement is designed as an assistance to the manual data replacement and it may not always result in optimal matches. 

When replacing the data inside the screen based on a Screen Template, you can only replace server data with server data, and local data with local data. The drag and drop data replacement accelerators do not work with the mixed data sources.

1. Drag and drop the entity, that has the data you want to use over the widget for which you want to replace the data.
2.  Check the **TrueChange** tab for errors and warnings and errors and fix them.
3.  Verify the widget labels correspond to the data and edit the labels or expressions if needed.
