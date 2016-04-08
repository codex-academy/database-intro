---
layout: default
---

# Data Modeling

The process of creating a set of data entities that describes a problem domain is called Data Modeling. When creating a data model you look at what different entities need to be stored and how they relate to each other. Entities are created as tables that contains rows. Each row contains some fields: the specific data that's being stored. and Fields can be used as keys (foreign keys) to map relationships between entities.

Look at this scenario:

> As as Taxi Owner I would like to see who is driving my taxis, and on which routes.

Answer these questions:

  * For what entities do we need to store data?
  * What data do we need for each entity?
  * How do the entities relate to each other?

Once the above questions are answered we have the basic information for creating a data model. From the data model we can create a database.
