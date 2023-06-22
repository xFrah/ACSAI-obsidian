- What is an entity?
- What is a relation?
- What constraints does serial represent?
- Draw the ER model
- Given an ER model, translate it into relational model
- Write a query specific to your database
- Write 3 triggers(one of them must use NEW keyword)

---

## Some definitions

> [!cite] Entity definition
> Entities represent classes of objects worthy of autonomous existence.

> [!cite] Schema definition
> A schema is basically a table.
> It's made up of the characteristics of the data.
> 
> Part of it changes with time, that would be the instances inside of it.

> [!cite] Relationship definition
> A relationship is a logical link between two entities.
> 
> Physically, relationship may be expressed without additional entities, but sometimes they are required.

> [!cite] Cardinality definition
> The cardinality of relationship describe the minimum and maximum number of occurrences of a relationship in which an entity occurrence can participate.
> 
> Example: 
> - A person can reside at least in 1 and at most in 1 city
> - A city can have a minimum of 0 and a maximum of 50000 residents
>   
> ![](../z_images/Pasted%20image%2020230622221813.png)

> [!cite] Attribute Domains definition
> Each attribute/column has a domain that defines the set of valid values for that attribute.

---

## ER vs Relational

### ER
The Entity-Relationship (ER) model is a conceptual data model. 

It is capable of describing the database requirements.

![](../z_images/Pasted%20image%2020230622220720.png)

### Relational
Meanwhile, the relational model is based on the concepts of tables and tuples.

![](../z_images/Pasted%20image%2020230622224033.png)

### Going from ER to Relational

We have to:

- Kill redudancies
- Kill generalizations
	- Merge child entities into the parent
	- Merging the parent into the child entities
	- Substitution with relationships
- Partitioning and merging of entities and relationships where it is convenient.
- Selection of keys

---

## Generalizations

![](../z_images/Pasted%20image%2020230622223127.png)

---

## Constraints

![](../z_images/Pasted%20image%2020230622230753.png)

- `NOT NULL` - Ensures that a column cannot have a NULL value
- `UNIQUE` - Ensures that all values in a column are different
- `PRIMARY KEY` - A combination of a `NOT NULL` and `UNIQUE`. Uniquely identifies each row in a table
- `FOREIGN KEY` - Prevents actions that would destroy links between tables
- `CHECK` - Ensures that the values in a column satisfies a specific condition
- `DEFAULT` - Sets a default value for a column if no value is specified
- `CREATE INDEX` - Used to create and retrieve data from the database very quickly

---

## Altering the database

### Insert

For selected columns:
![](../z_images/Pasted%20image%2020230622231636.png)

For all columns:
![](../z_images/Pasted%20image%2020230622231701.png)


### Update

![](../z_images/Pasted%20image%2020230622231733.png)


### Delete

![](../z_images/Pasted%20image%2020230622231849.png)
