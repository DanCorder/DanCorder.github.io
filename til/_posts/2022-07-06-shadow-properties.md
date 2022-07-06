---
layout: til
title: "EF Core Shadow Properties"
---

EF Core has a feature called ["Shadow Properties"](https://docs.microsoft.com/en-us/ef/core/modeling/shadow-properties). These are values that exist in the database but aren't declared on the entity class.

This can be useful for defining foreign key columns when you don't want the foreign key values in your entity classes. I'd need to experiment on a larger codebase, but this could be a nice way of keeping database and business code separate without having to declare two sets of model classes and mapping between them.

For example a `Parent` class has a property of type `Child`.

In the `OnModelCreating` method of the DbContext we can declare a column on the `Child` entity to hold the ID of its parent, and then set up a foreign key to use the column.

```
modelBuilder.Entity<Child>()
            .Property<int>("ParentId");

modelBuilder.Entity<Child>()
            .HasOne<Parent>()
            .WithOne(d => d.Child)
            .HasForeignKey<Child>("ParentId")
            .IsRequired();
```
