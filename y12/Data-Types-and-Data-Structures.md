### Data Types and Data Structures

Data types represent the kind of data being handled, such as integers, floats, or strings. Data structures are ways to organize and store data efficiently. Examples include arrays, linked lists, and trees. Data structures rely on underlying data types to define their operations and functionality.

**Examples include**:
- Linear Structures: Arrays, Linked lists, Queues, Stacks.
- Non-linear Structures: Trees, graphs, Heaps.

<br><br>

#### Static Data Structures

Static data structures have fixed memory allocation, meaning their size is determined at compile time. Examples include arrays and fixed-size records. They are efficient for known, fixed-size datasets but lack flexibility for dynamic operations

**Advantages:**
- Predictibility: Memory requirements are known ahead of time
- Speed: Accessing elements is faster as memory is pre-allocated

**Disadvantages:**
- flexibility: Size cannot be adjusted during runtime
- Wastage: May reserve more memory than needed, leading to efficiency

<br><br>

#### Dynamic Data Structures

Dynamic data structures can grow or shrink during runtime, making them more flexible. Examples include linked lists and dynamic arrays. These structures are useful for unpredictable data sizes but may introduce memory management overhead.

**Examples include:**
- Linked Lists: Nodes connected via pointers.
- Dynamic Arrays: Automatically resize as elements are added/removed.
- Binary Trees: Data is stored hierarchically.

**Advantages:**
- Flexibility: Adapt to data changes without memory wastage.
- Efficient Memory Usage: Only required memory is allocated.

**Disadvantages:**
- Overhead: Requires additional memory for pointers/metadata.
- Complexity: More challenging to implement and debug compared to static structures.

<br><br>

#### Built-in Data Structures


These are pre-defined, optimized data structures provided by programming languages.

**Examples in Python include:**
- Lists: Dynamic arrays that can hold any data type.
- Dictionaries: Store key-value pairs for fast lookups.
- Sets: Collections of unique elements with fast membership checks.
- Tuples: Immutable sequences of elements.

**Advantages:**
- Ease of Use: Built-in methods simplify operations like insertion, deletion, and sorting.
- Efficiency: Optimized implementations for better performance.

**Disadvantages:**
- Limited to the capabilities and constraints defined by the language.

<br><br>

#### Relationship Between Data Structures and Algorithms


Data structures provide the foundation for algorithms to manipulate data efficiently. The choice of data structure directly impacts algorithm performance, such as time and space complexity.

**Examples of Relationships:**
- Sorting Algorithms: Operate on arrays, lists, or trees.
- Graph Algorithms: Utilize adjacency matrices or adjacency lists for traversal (e.g., BFS, DFS).
- Dynamic Programming: Often relies on tabular data structures like 2D arrays.

**Efficiency:**
- Proper data structure selection optimizes algorithm performance and reduces complexity.

<br><br>

#### More On Data Structures

- List

- Dictionary
<br><br>

- **Stacks**
  
  First in and Last out (FILO) data structure. Items can be added to the top taken away from the top

  Push - Add item to top
  
  Pop - Remove an item from top and return
  
  Peek - Return item at the top of stack but not removed
  
  isEmpty - Return true if empty
  
  isFull - Returns true if full
  
  Spaces_left - Return how many spaces to the left
<br><br>

- **Queues**
  
  First in first out (FIFO) data structure
  
  Items are added to rear of queue and removed from the front 
  
  Enqueue - Add item 
  
  Dequeue - remove item 
  
  isEmpty - Return true if empty
  
  isFull - Returns true if full
  
Spaces_left - Return how many spaces to the left
<br><br>
- Graphs

- Tree

- Hash Tables 
<br><br>

Static structure = Fixed size

Dynamic structure = dynamic sie and can be modified
<br><br>

#### The Heap

( It’s a dynamic memory ) A memory area from which computers can request contiguous memory sections at program runtime and release them again in any order

A large pool of memory available for use by the program at runtime.


