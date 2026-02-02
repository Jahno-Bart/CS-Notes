## Dictionaries and Hash Tables 


### Hash Table:

A hash table is a data structure designed for efficient data retrieval. It works by mapping keys to values using a process called hashing.
<br><br>
**Hashing:**

- A hash function converts input data (keys) into a fixed-size integer, typically an index for an array.

- For example, if you hash the word "cat," the hash function might map it to index 5 in the array.
<br><br>

**Uses of Hash Tables:**

- Fast data retrieval (average time complexity O(1)O(1)O(1) for lookups).

- Implementation of associative arrays (e.g., Python 	dictionaries, Java HashMap).

- Database indexing to speed up searches.
<br><br>

**Collisions:**

- Collision occurs when two keys produce the same hash value.

- Example: If "abc" and "xyz" both hash to index 2, we have a collision.

<br><br>

**Collision Handling Techniques:**

- Closed Hashing
    - Linear probing - after the hash search the data structure linearly for the next free locations
    - Quadratic Probing - after the hash search the data structure in quadratic interval
    - Double Hashing - Hash the result with a different hashing algorithm to find a new location 
<br><br>
- Chaining
    - Store multiple key-value pairs at the same index using a linked list or other structures
<br><br>

- Open Addressing
    - Probe other indices in the array to find an open slot
<br><br>

**Rehashing:**

  - When the hash table becomes too full, rehashing resizes the table to maintain efficient
  - Example: Doubling the size of the array and redistributing the existing entries using a new hash function

**Applications:**

- Symbol tables in compilers
- Caching (e.g., LRU cache in operating systems)
- Implementation of sets
<br><br>
<br><br>

## Dictionaries

A dictionary is a collection of key-value pairs in which the value is accessed via the associated key. It is a high-level implementation of a hash table commonly used in programming

A dictionary is a high-level abstraction of a hash table, typically available in may programming languages.
<br><br>

**Structure:**
- A collection of key-value pairs.

Each key is unique, and the value is accessed using the key
<br><br>

**Example:**
```python 
my_dict = {"name": "Alice", "age": 25, "city": "New York"}
print(my_dict["age"]) # Ouputs 25
```
<br><br>

#### Features of dictionaries:
- **Dynamic:** They grow or shrink as key-value pairs are added or removed.

- **Fast operations:** Insert, delete, and lookup operations are typically O(1)O(1)O(1) on average.
<br><br>
#### Applications
- **Data Analysis:** Stores counts or aggregate data

- **Example:**

```python 
text = "The green, green grass grows"
word_counts = {}
for word in text.lower().split():
    word_counts[word] = word_counts.get(wordm 0) + 1
    print(word_counts)
# Output: {'the': 1, 'green': 2, 'grass': 1, 'grows': 1}
```

- Configuration Storage: Store settings or parameters (e.g., JSON-like data structures).
- Graphs: Represent  adjacency lists.
<br><br>

#### Handling Edge Cases:
- Missing Keys: Use methods like get() in python to handle missing keys gracefully
- Nested Dictionaries: Enable representation of hierarchical data

```python
person = {"name": "Alice", "address": {"city": "New York", "zip": "10001"}}
print(person["address"]["city"]) # Outputs: New York

```
#### Applications:
- Web Development: Store sessions data or API responses
- Machine Learning: Feature extraction and mapping
