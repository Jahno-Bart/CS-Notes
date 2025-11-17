## Abstraction & Automation
<br><br>

#### Representational Abstraction

Process of removing unnecessary details from a real-world problem and representing only the essential information

#### Abstraction by Generalisation 

Process of combining several similar objects, processes, or ideas into a single, more general representation by identifying the common characteristics they share.

It reduces complexity by grouping related things under a general category instead of treating each one seperately

**Example:**

Instead of separately defining car, bus , and motorbike, you generalise them into a single class, such as a **vehicle**, because they share common features.
<br><br>

#### Procedural Abstraction

Abstracting away the actual values used in any particular computation, resulting in a "procedure". Focusing on something that is about what it does rather than how it does it.

**Example:**

You might have a procedure `CalculateArea(width, height)` which hides the formula `width * height` inside. Users of the procedure only need to pass `width` and `height` and get back the area, they dont need to know how the multiplication is implemented each time.

**Exam help**

- Represents a computational method
- it involves ignoring or hiding the specific values and focusing on general patter of computation
- It adds modularity , code reuse and simplifies the design of algorithms
<br><br>

#### Functional Abstraction

Functional abstraction is when you define a function in such a way that you hide the internal method of how it works, focusing only on what the function does (its interface) rather than how it does it.

In functional abstraction, the details of how a computation is carried out are hidden. You can think of a function as a black box – it takes an input (or set of inputs)

**Example:**

Imagine you have a block of code that sorts a list of student grades, prints them, computes the average, and finds the highest score. Without abstraction you might do all these in one place.
Using procedural abstraction, you might create procedures like `SortList()`, `PrintList()`, `ComputeAverage()`, `FindHighest()`.
Using functional abstraction, you might define a function `GetStatistics(gradesList)` which returns an object (or tuple) with average, highest, lowest, etc., without worrying about how the grades were sorted or scanned. Users call `GetStatistics()` and get results — the internal sorting/scanning method is hidden.


**Exam help**

- Functional abstraction comes after procedural abstraction: you first abstract a computational method into a procedure (procedural abstraction), then abstract further into a function by hiding the method entirely.

- It emphasises hiding ‘how’ the computation is done, so other parts of the system can invoke the function without worrying about internal details.

- Benefits include: easier maintenance, clearer interfaces, reusability of functions, and simpler higher-level design (you treat functions as black-boxes).

- In an exam you might be asked to identify which type of abstraction is being used
    - hide a method -> functional abstraction
    - break a problem into procedures -> procedural abstraction
    - combine similar objects -> abstraction by generalisation
    - hide data representation -> data abstraction
<br><br>

#### Data Abstraction

Data abstraction is the process of hiding the internal representation of data (how it’s stored, how it’s built) and exposing only the essential features and operations that matter to the user or other parts of the system.

- Users interact with data types, operations on them, without needing to know how those data types are implemented internally
- Internals such as memory layout, pointer structure, tree vs array, etc., are hidden 
- This yields code modularity, maintainability, flexibility because you can change how a data onject is built, while keeping the interface consistent

**Example:**

Suppose you have a data object Queue. From a user perspective you have operations: `enqueue(item)`, `dequeue()`, `isEmpty()`. You don’t know (and don’t need to know) whether internally it’s implemented as an array with two indices, or a linked list with pointers. That internal detail is hidden — that’s data abstraction in action.

If later the implementation changes from array to linked list for performance reasons, the code using Queue need not change. The abstraction remains consistent.

**Exam help**

- Data abstraction hides the representation details of data. AQA: “details of how data are actually represented are hidden…”

- It allows the construction of new kinds of data objects from existing types.

- It is different from procedural and functional abstraction: those deal with methods and computations; data abstraction deals with how data objects are represented and used.

- When you see phrases such as “we treat the structure as a black-box”, “we don’t care how it’s stored”, “just use its operations”, that typically indicates data abstraction.

- When implementing data abstraction, you might use abstract data types (ADTs), classes-with-hidden-fields, or modules exposing operations but hiding internal representation.

- For AQA you should be able to recognise examples: e.g., a stack abstract data type where you only see push, pop, isEmpty but you don’t see whether it’s implemented using an array or a linked list.

- A memorisable definition:
    - “Data abstraction: the storage and representation of data in a computer system along with its logical description and interaction with operators. This allows the construction of new compound data objects from existing ones.”
<br><br>
----------

### Functional Decomposition

**Functional Decomposition:** Breaking up a problem into many smaller problems which can themselves be decomposed further, or are small enough to solve


