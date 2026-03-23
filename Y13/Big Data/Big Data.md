
---

## What is Big Data?

**Big Data** is a catch-all term for datasets so large or complex that they cannot be processed or stored using traditional data management tools (e.g. a single relational database on a single server).

> **Key point:** "Big" is a _relative_ term — a dataset is "big" when it can no longer fit onto a single server or be processed by conventional means.

---

## The Three V's of Big Data

Big Data is characterised by three properties:

|Property|Description|Example|
|---|---|---|
|**Volume**|Data too large to fit on a single server|Petabytes of social media posts|
|**Velocity**|Data generated and needed at high speed; milliseconds to seconds to respond|Live stock market feeds, GPS tracking|
|**Variety**|Data in many forms — structured, unstructured, text, multimedia|Tweets, videos, sensor readings, logs|

### Volume

- Data may span many terabytes or petabytes.
- Cannot be stored on or processed by a single machine.
- Requires **distributed storage and processing** across multiple machines.

### Velocity

- Data is _continuously streamed_ from sources such as:
    - Networked sensors (IoT devices)
    - Smartphones
    - Video surveillance systems
    - Mouse clicks and web interactions
- Systems must process and respond in near real-time.

### Variety

- **Structured data**: fits neatly into rows and columns (e.g. traditional databases).
- **Unstructured data**: has no predefined format (e.g. emails, images, videos, social media posts).
- **Semi-structured data**: partially organised (e.g. JSON, XML).

> **Most difficult aspect:** Despite volume getting all the attention, the **lack of structure** is the hardest challenge — it makes data analysis significantly more difficult and means relational databases are inappropriate.

---

## Why Relational Databases Are Unsuitable

Relational databases:

- Require data to fit into a **row-and-column (tabular) format**.
- **Do not scale well** across multiple machines (poor horizontal scalability).
- Struggle with unstructured or semi-structured data.
- Are designed for consistency and structure — the opposite of what Big Data often looks like.

---

## Distributed Processing

When data is too large for a single server:

- Processing **must be distributed** across more than one machine.
- Each machine handles a portion of the data in parallel.
- Results are then combined.

### MapReduce (context)

A common paradigm for distributed processing:

- **Map phase**: Split the problem and process chunks of data in parallel across nodes.
- **Reduce phase**: Aggregate the results from all nodes into a final answer.

---

## Functional Programming as a Solution

**Functional programming (FP)** is particularly well-suited to Big Data processing because it makes it easier to write both **correct** and **efficiently distributed** code.

### Key Features of Functional Programming

#### a) Immutable Data Structures

- Once created, data **cannot be changed** (no mutation).
- Eliminates side effects caused by shared, mutable state.
- Makes it safe to process data in parallel across multiple machines — no risk of one thread corrupting another's data.

#### b) Statelessness

- Functions do not rely on or modify external state.
- Each function call depends only on its **inputs** and always produces the same **output** (referential transparency).
- Stateless functions can be safely run on any machine in a cluster without coordination overhead.

#### c) Higher-Order Functions

- Functions that take other functions as arguments or return functions as results.
- Examples: `map`, `filter`, `reduce`.
- Enable concise, reusable, and composable data transformations.
- Naturally model the kinds of operations applied across large datasets.

### Why Functional Programming Makes Code Correct

- No shared mutable state → no race conditions.
- Pure functions are easier to test and reason about.
- Side-effect-free → behaviour is predictable.

### Why Functional Programming Makes Code Distributable

- Stateless functions can run on any server independently.
- Immutable data can be safely shared across nodes without locking.
- Higher-order functions like `map` and `reduce` naturally parallelised across partitions of data. Many processors can work simultaneously on parts of a dataset without affecting other parts


---

## Machine Learning and Big Data

- Because of the **lack of structure**, traditional query-based analysis is insufficient.
- **Machine learning techniques** are needed to:
    - Discern patterns in large, unstructured datasets.
    - Extract useful, actionable information.
    - Build predictive models (e.g. recommendation engines, fraud detection).

---

## Fact-Based Model for Representing Data

A **fact-based model** represents data as a collection of atomic, indivisible facts.

### Key Principles

- Each **fact** captures a **single piece of information (Atomic fact)**.
- Facts are typically **immutable** - once recorded, they are not changed or deleted; new facts are added instead and kept eternally true by the use of timestamps.
- This mirrors the functional programming principle of immutability.
- Each fact is identifiable so that duplicate facts can be identified
- Where you have identical facts you can create a random 64-bit number to distinguish between them

### Example

Rather than storing a row like:

|UserID|Name|Email|
|---|---|---|
|001|Alice|alice@example.com|

A fact-based model stores:

- `(001, has-name, "Alice")`
- `(001, has-email, "alice@example.com")`

Each tuple is a separate, standalone fact.

### Advantages

- Highly flexible — easy to add new types of facts without restructuring.
- Works well with unstructured and varied data.
- Natural fit for distributed systems.


### Fault Tolerance & Truth

So in a relational database, if the data changes we update the record
If that update was a mistake we are reliant on backups to try to get back to the previous value

In a fact base model, you can just delete the false information
In which case the previous fact is now the most recent

Or you can just establish a new fact
So the fact based model is far more tolerant of human faults

As well as that we have the concept of data being forever true. Each fact is true even if there is a more recent fact, the previous fact is true it just has a limited scope for its truth. So we can say that in the Fact Based Model, data is True forever.


---

## Graph Schema

A **graph schema** is used to capture the **structure** of a dataset in a fact-based model.

### Components of a Graph Schema

| Component      | Description                        | Example                         | Shape                                         |
| -------------- | ---------------------------------- | ------------------------------- | --------------------------------------------- |
| **Nodes**      | Entities or objects in the dataset | A person, a product, a location | *Oval*                                        |
| **Edges**      | Relationships between nodes        | "Alice **purchased** Book X"    | *Solid lines*                                 |
| **Properties** | Attributes of nodes or edges       | Node property: `name = "Alice"` | *Rectangular box* connected by *dotted lines* |

### Nodes

- Represent **entities** (things that exist).
- Each node has a unique identifier.
- Can have properties (key-value pairs describing attributes).

### Edges

- Represent **relationships** between two nodes.
- Are **directed** (have a start and end node).
- Can also have properties (e.g. the date of a transaction).

### Properties

- Key-value pairs attached to **nodes or edges**.
- Provide additional detail about an entity or relationship.

### Example Graph Schema

```
[Alice] ---purchased---> [Book: "1984"]
         (date: 2024-01-10)

[Alice] ---lives-in---> [City: London]
```

- Nodes: Alice, Book, City
- Edges: purchased, lives-in
- Properties: date on the purchased edge; title on the Book node

### Why Graph schemas for Big Data?

- Relational schemas are rigid; graph schemas are **flexible**.
- New node types or relationships can be added without restructuring.
- Excellent for representing **highly connected, varied data** (e.g. social networks, recommendation systems).

---

## Case Study - Tesco

Tesco are processing, nationally hundreds of transactions every second. I a traditional database you might get to cope with 30 requests per second.

But if you realise that you only need to store a transaction then you can reduce the time greatly, especially if you store it in a unstructured manner

Then you can perform a process of analysis (data mining) in batch jobs during quiet periods, or even take a snapshot of the data to then analyse.
<br>

### Tesco - cont'd

Because of this Tesco could look at patterns such as when is the best time to put something on sale etc.

But it was the advent of the clubcard that really gave them power (and they gathered all the data before they knew what they might do with it, or if it was even possible to do anything with it)

- - -
## Summary Table

|Concept|Key Point|
|---|---|
|Big Data|Data too large/complex for traditional tools|
|Volume|Too large for a single server|
|Velocity|Streamed continuously, near real-time|
|Variety|Structured, unstructured, multimedia|
|Main challenge|Lack of structure, not just size|
|Relational DBs|Not suitable — require tabular format, poor scalability|
|Distributed processing|Spread across multiple machines|
|Functional programming|Immutability, statelessness, higher-order functions|
|Immutability|Safe parallel processing, no race conditions|
|Statelessness|Functions runnable on any node independently|
|Higher-order functions|map, filter, reduce — natural parallelism|
|Machine learning|Finds patterns in unstructured data|
|Fact-based model|Each fact = one atomic piece of information|
|Graph schema|Nodes, edges, properties capture dataset structure|

---
