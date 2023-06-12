The entity-relationship model is a data model that provides a series of constructs that are capable of describing the data structure of an application.

![](../z_images/Pasted%20image%2020230612110950.png)

---

## Entity

An entity represent a class of objects worthy of autonomous existence for context purposes.
An instance of an entity is an object of the class that the entity represents.

![](../z_images/Pasted%20image%2020230612112714.png)

---

## Attributes

Attributes describe properties of interest to the entities and associate each entity instance with a value of a certain type (attribute domain).

![](../z_images/Pasted%20image%2020230612112701.png)


### Cardinality of attributes

Cardinality of attributes describes the minimum and maximum number of attribute values associated with each entity or relationship occurrence.

![](../z_images/Pasted%20image%2020230612144549.png)

If the cardinality is (1,1) it is omitted (it is the default option) If null we use minimum cardinality 0.

---

## Relationships

Association (or relationship) represent logical links, of interest for the context to be modeled, between two or more entities.

![](../z_images/Pasted%20image%2020230612113504.png)


Association is a subset of the Cartesian product between the instances of the entities involved.

![](../z_images/Pasted%20image%2020230612123031.png)

> [!info]
> There cannot be two instances of rel that bind the same pair of entities.

> [!note]
> Relationships can involve more than two entities
> 
> ![](../z_images/Pasted%20image%2020230612124457.png)


### Cardinality of relationships

The cardinality of relationship describe the minimum and maximum number of occurrences of a relationship in which an entity occurrence can participate.

For example, a person can have only 1 relationship with a city of residence.

