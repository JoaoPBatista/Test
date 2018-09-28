---
summary: Define the referential integrity behavior you wish to have in entity relationships.
---

# Delete Rules

When you are creating relationships between the entities in your module, you can define which kind of referential integrity you want to use when deleting records. The referential integrity specifies what happens to an Entity `B` record that references an Entity `A` record, when the Entity `A` record is deleted.

To specify the referential integrity rule you want to use, you have set the "Delete Rule" property of the [reference attribute](<intro.md>), which corresponds in database terminology to a foreign key. 

The possible values of this property are:

* `Protect`;
* `Delete`;
* `Ignore`.

Check below for an explanation of each value.


## "Protect" Delete Rule

This value prevents deleting records in Entity `A` while there are associated records in Entity `B`, assuming that there is a relationship between Entity `A` and Entity `B` and that the reference attribute is in Entity `B`. If you try to delete a record in Entity `A` that still has associated records in Entity `B`, the Platform Server returns a database exception and this operation is not executed.

To implement **Protect** behavior, set the "Delete Rule" property of the reference attribute with the `Protect` value. As a consequence, a database constraint on the reference attribute will be created.

`Protect` is the default value of the "Delete Rule" property in relationships between entities of your module and/or entities exposed by other modules.

Service Studio allows you to use the **Protect** delete rule in relationships between entities that are stored in platform database and, therefore, referential integrity can be guaranteed. When creating relationships between your entities and entities references, you must be aware that the **Protect** rule can only be used when the producer of the entity reference is a module. Otherwise, the delete rule must be **Ignore**.

### Example

A business rule states that an `Order` belongs to one and only one `Customer` and that a `Customer` may have one or more `Orders`; therefore, between these entities there is a One-To-Many relationship and `Order` has a reference attribute `CustomerId` to `Customer`.

Another business rule says that a `Customer` cannot be deleted if there are `Orders` associated with it. Therefore, to delete a `Customer`, you would have to delete all the `Orders` the `Customer` placed before deleting it.

To implement these business rules, edit the `CustomerId` attribute from the entity `Order` and set the "Delete Rule" property to `Protect`.

## "Delete" Delete Rule

Deleting records in Entity `A` implies that all the related records in Entity `B` are also deleted, assuming that there is a relationship between Entity `A` and Entity `B` and that the reference attribute is in Entity `B`. This mechanism is commonly known as Cascade Delete.

To implement the **Delete** behavior you simply have to set the "Delete Rule" property of the reference attribute to `Delete`. As a consequence, a database constraint on the reference attribute will be created.

Service Studio allows you to use the **Delete** delete rule in relationships between entities that are stored in a platform database and, therefore, referential integrity can be guaranteed. When creating relationships between your entities and entities references, you must be aware that the **Delete** rule option can only be used when the producer of the entity reference is a module. Otherwise, the delete rule must be **Ignore**.

### Example

A business rule states that an `Order_Item` belongs to one and only one `Order` and that an `Order` has one or more `Order_Items`; therefore, between these entities there is a One-To-Many relationship and `Order_Item` has a reference attribute `OrderId` to `Order`.

Another business rule says that when an `Order` is deleted, all the associated `Order_Item` are also deleted.

To implement these business rules, edit the `OrderId` attribute from the entity `Order_Item` and set the "Delete Rule" property to `Delete`.


## "Ignore" Delete Rule

Deleting records in Entity `A` means that only the records in Entity `A` are deleted, even if there are related records in Entity `B`, assuming that there is a relationship between Entity `A` and Entity `B` and that the reference attribute is in Entity `B`.

**Ignore** is the default value of the "Delete Rule" property in relationships between an entity of your module and an entity exposed by extensions.

Since this type of delete rule does not require any database constraints, you can use it in relationships between your entities and any entity you added as a reference to your module, no matter if its producer is a module or an extension.

This delete rule does not guarantee referential integrity and, therefore, no constraints are created in the database. Accordingly, when a reference attribute "Delete Rule" property is changed to `Ignore`, the corresponding automatic index is deleted unless any of its properties have changed.

### Example

A business rule states that every operation or change of status of any `Order` must be logged in `Order_History`.

One `Order_History` concerns one and only one `Order` and one `Order` has one or more `Order_History`; therefore, between these entities there is a One-To-Many relationship and `Order_History` has a reference attribute `OrderId` to `Order`.

The business keeps an `Order_History` even when the respective `Order` has been deleted.

To implement these business rules, edit the `OrderId` attribute from the entity `Order_History` and set the "Delete Rule" property to `Ignore`.
