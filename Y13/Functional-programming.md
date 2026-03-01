#Functional Programming

**Functional programming** is an approach to programming that is built around the concept of **pure functions**. These are functions that do not modify data. The functional paradigm has no variables, and no function shares data with any other function.

A **pure function** will take data as input and produce new data as output.

Functions can be combined to carry out a complex sequence of tasks.<br>

**Haskell** is a popular function programming language<br><br>


## What is functional programming

Functional programming is a **declarative paradigm** where you describe _what_ to compute rather than _how_, similar to mathematical functions. Key characteristics include:

- **Statelessness** — functions always return the same output for the same inputs, with no reliance on changing global state
- Functions can be built from other functions or call themselves **recursively**
- Originated with **Lisp (1958)**; notable functional languages include Haskell, Erlang, and Scheme
- Many modern languages (Python, JavaScript, Java, etc.) also **support functional programming**, though they aren't purely functional
- Contrasts with **procedural programming**, where program state can affect function outputs unpredictably


#### Benefits of the functional programming paradigm

1. Supporting the decomposition and abstraction of computing problems into **functions** that made up of other functions that are made up of other functions, and so on
2. Being suitable for running parallel and concurrent program execution, which allows functional programs to run on multiprocessor systems<br><br>

- - -

## Haskell

#### Declaring values

**Core Concept:** In Haskell, you use the `=` operator to declare values and bind them to identifiers (e.g., `my_pi = 3.14`).

**Immutability:** Unlike variables in procedural programming, Haskell values are **immutable** — once declared, they cannot be changed. Attempting to redeclare the same value in a file will produce an error.<br>


- Declaring a value in Haskell is closer to declaring a **constant** in procedural languages
- It's similar to a mathematical variable that remains fixed throughout a calculation
- Comments use `--`

**Command Line vs. Files:**

- In files (`.hs`), redeclaring a value causes an error
- On the command line, it _appears_ to allow redefinition, but it's actually treating each declaration as a separate, unrelated value

**Best Practice:** Declare values within functions to ensure they're properly checked during compilation and execution, avoiding potential issues.<br><br>


#### Writing functions

Here's a summary of Haskell's static typing and function definitions:

**Static Typing:**
Haskell uses **static typing**, meaning the type of every parameter and return value is determined at compile time. This gives you better control over how functions are translated and executed.<br><br>

**Base Types:**
Common base types (capitalized) include `Integer`, `Float`, `Double`, `Bool`, and `Char`.<br><br>

**Function Definition Syntax:**

A function definition specifies the function name, input types, and output type:
```haskell
is_magic :: Integer -> Bool
is_magic x = (if x == 3 then True else False)
```

The `::` operator declares the function type. Type enforcement ensures only correct inputs are accepted; anything else returns an error.<br><br>

**Multiple Parameters:**

For functions with multiple parameters, list each input type followed by the output type (which is always last):

```haskell
power_of :: Integer -> Integer -> Integer
power_of x y = x^y
```
<br>

**Pattern Matching:**

A powerful feature where functions match arguments against defined patterns from top to bottom:
```haskell
abc :: Char -> String
abc 'a' = "Apple"
abc 'b' = "Boat"
abc 'c' = "Cat"
abc _ = "Zebra"  -- default case
```

Pattern matching produces cleaner code than multiple selection statements in procedural languages.<br><br>

- - -

## Function types

A **function** is a rule that maps inputs from one set (domain/SetA) to outputs in another set (co-domain/SetB). Key points:<br>

- **Requirement**: Every input must map to exactly one output, but not all possible outputs need to be used
- **Domain**: The set of all possible inputs
- **Co-domain**: The set of all possible outputs
- **Range**: The set of actual outputs produced by the function

Example: `double_number`

- **Domain**: Natural numbers (ℕ)
- **Co-domain**: Natural numbers (ℕ)
- **Range**: Even natural numbers (subset of co-domain)
- Note: Odd numbers like 3 can never be outputs, since doubling any natural number always produces an even result

<br>

 **Function Type Notation**

Functions are written as `f: A → B`, meaning function `f` maps type A to type B. In programming languages like Haskell, this is written as `functionName :: InputType -> OutputType`.<br>

![[Pasted image 20260301172514.png]]

#### Domain and co-domain

**Key Definitions:**
- **Domain**: The set of all possible inputs
- **Co-domain**: The set of all possible outputs (may include unused values)
- **Range**: The set of actual outputs produced by the function

**Important**: Domain and co-domain don't have to be the same data type.<br><br>

**Examples**

**Sine Function:**

- Domain: Real numbers (ℝ)
- Co-domain: Real numbers (ℝ)
- Range: Real numbers between -1 and 1 (inclusive)

**is_prime Function:**

- Domain: Natural numbers (ℕ)
- Co-domain & Range: Boolean values (True/False)

The sine example shows a function where domain and co-domain are the same type, while `is_prime` demonstrates how they can differ—converting numbers into Boolean results.<br><br>

![[Pasted image 20260301172854.png]]

#### Function type

**Function Type Basics:** A function type describes the mapping from input type to output type using the notation `f: A → B`, where:

- `f` is the function name
- `A` is the input (argument) type
- `B` is the output (result) type

**General Examples:**

- `double_number: Integer -> Integer`
- `is_prime: Integer -> Boolean`
<br>

**Haskell Syntax:** Haskell uses a double colon (`::`) followed by the input and output types:

`functionName :: InputType -> OutputType`
<br>
**Haskell Examples:**

- `is_correct_password :: String -> Boolean` — takes a password string, returns True/False
- `phone_number_search :: String -> Integer` — takes an account name string, returns a phone number

The function type encapsulates both the domain and co-domain, making it clear what data types a function accepts and produces.<br><br>

- - -

## First class objects

**First-class objects** are programming entities that can:

- Appear in **expressions**
- Be assigned to **variables**
- Be used as **arguments**
- Be **returned** by functions

Use the acronym **EVAC** to remember these four capabilities.<br>

#### Key Points

- **Primitive types** (integers, strings) are first-class objects in procedural programming
- **Functions** are first-class objects in functional programming
- In some procedural languages like Python, functions can also be first-class objects<br>

#### Higher-Order Functions

A **higher-order function** is one that accepts another function as an argument. For example:

`applyTwice(doubleNumber, 10)`

This passes the `doubleNumber` function to `applyTwice`, which applies it twice: `doubleNumber(doubleNumber(10))` = 40.<br>

#### Practical Example

Functions can be passed as arguments and executed within other functions:

`speak(shout, "Hello World")  // outputs: HELLO WORLD`

Here, the `shout` function is passed to `speak`, which then calls it with the provided text.<br><br>

- - -

## Function application

Calling a function with all its required arguments at once.  
Examples:

```haskell
power_of 4 3    → 64   -- 4^3
add_these 4 3   → 7    -- 4 + 3
rectangle_surface 50.3 13.8 → 694.14  -- 50.3 × 13.8
```

Function type signatures show input → output:

```haskell
power_of :: Integer -> Integer -> Integer
rectangle_surface :: Float -> Float -> Float
```


#### **Partial Application**

Applying **fewer than all arguments**, which returns a **new function** expecting the remaining arguments.<br><br>

**Why it matters:**

- Haskell treats **all functions as taking one argument** — multiple arguments are handled via nested partial applications.
- This enables **function currying** and **reusable intermediate functions**.

 Example: `rectangle_surface`

```haskell
rectangle_surface :: Float -> Float -> Float
-- Can be read as: Float -> (Float -> Float)

> (rectangle_surface 50.3) 13.8   → 694.14
> result = rectangle_surface 50.3
> result 13.8                   → 694.14
```

Here, `rectangle_surface 50.3` returns a function that expects one more `Float` and returns a `Float`.<br><br>

#### **Multi-Argument Partial Application: `box_vol`**

Function:

```haskell
box_vol :: Integer -> Integer -> Integer -> Integer
box_vol x y z = x * y * z
```

Can be applied step-by-step:

```haskell
> partial_volume = box_vol 4          -- returns: Integer -> Integer -> Integer
> volume = partial_volume 5           -- returns: Integer -> Integer
> volume 9                          → 180  -- 4 × 5 × 9
```

Function type breakdown:

```haskell
box_vol :: Integer -> (Integer -> (Integer -> Integer))
```

Each application returns a function awaiting the next argument.<br><br>


#### **Key Takeaway**

Partial application is **not optional syntax** — it’s **fundamental to Haskell’s design**. Every multi-argument function is actually a chain of single-argument functions, enabling powerful composition and abstraction.

This is the essence of **currying** in functional programming.<br><br>

- - -

## Function composition

**Function composition** combines two functions into one by connecting the output of the first function to the input of the second. It's denoted as **g ∘ f** (read as "g composed with f").<br><br>

#### Key Requirement

For composition to work, the **co-domain of f must match the domain of g**:

- If `f: A -> B` and `g: B -> C`
- Then `g ∘ f: A -> C`
<br>

#### How It Works

The composition `g ∘ f` is equivalent to `g(f(y))` — you calculate `f` first, then pass its output to `g`.

**Example:**

- `f(y) = y + 6`
- `g(x) = x / 2`
- `g ∘ f` with input `y = 3`:
    1. `f(3) = 9`
    2. `g(9) = 4.5`
    3. Result: `4.5`
<br><br>
#### In Haskell

Use the full stop (`.`) operator:

```haskell
g x = x / 2
f y = y + 6

(g.f) 3        -- Returns 4.5

h = g.f        -- Define h as the composition
h 5            -- Returns 5.5
```

The composition creates a new function that transforms the input type of `f` directly to the output type of `g`.<br><br>

- - -

## Lists in functional programming<br><br>

### Recursive Structure of Lists

#### Empty List

A list can be empty:

```haskell
[]
```

The empty list has no head and no tail.<br>

- - -

#### Head and Tail

A non-empty list is defined as:
```haskell
x : xs
```

Where:
- `x` = head (first element)
    
- `xs` = tail (remaining list)
    

Example:
```haskell
[1,2,3] == 1 : [2,3]
```

Important:
- The head is a single element.
- The tail is always another list.
- This recursive structure is central to functional programming.<br><br>

- - -

### Core List Operations

#### Return the Head
```haskell
head [4,3,5]
-- Result: 4
```

Returns the first element of a list.<br><br>

- - -

#### Return the Tail
```haskell
tail [4,3,5]
```

Returns the list without its first element.<br><br>

- - -

#### Test for Empty List
```haskell
null []  
-- Result: True  
  
null [1,2]  
-- Result: False
```

Used to check whether a list contains no elements.<br><br>

- - -

#### Return Length
```haskell
length [1,2,3]
-- Result: 3
```

Counts the number of elements in the list.<br><br>

- - -

#### Prepend (Add to Front)

Prepending is efficient in functional languages:

```haskell
1 : [2,3]  
-- Result: [1,2,3]
```

This creates a new list. The original list is unchanged.<br><br>

- - - 

#### Append (Add to End)

Appending uses the concatenation operator `++`:

```haskell
[1,2] ++ [3]  
-- Result: [1,2,3]
```

Appending is less efficient than prepending because the first list must be traversed.<br><br>

- - -

### Recursion Over Lists

Pure functional programming avoids loops. Lists are processed using recursion.

**Example:** Sum of a List

```haskell
sumList :: Num a => [a] -> a  
sumList [] = 0  
sumList (x:xs) = x + sumList xs
```

Explanation:
- Base case handles the empty list.
- Recursive case splits into head and tail.<br><br>

**Example:** Calculate Length Recursively

```haskell
lengthList :: [a] -> Int  
lengthList [] = 0  
lengthList (_:xs) = 1 + lengthList xs

```

`_` means the head value is ignored.<br><br>

- - - 

### Higher-Order Functions on Lists

Higher-order functions take functions as parameters and commonly operate on lists.

#### map

Applies a function to every element:

```haskell
map (*2) [1,2,3]  
-- Result: [2,4,6]
```

#### filter

Selects elements that satisfy a condition:

```haskell
filter (>3) [1,4,2,5]  
-- Result: [4,5]
```


#### fold (reduce)

Combines elements into a single value:

```haskell
foldr (+) 0 [1,2,3]  
-- Result: 6
```

`foldr` processes the list recursively from the right.<br><br>

- - -

### Key Characteristics of Lists in Functional Programming

#### Immutability

Lists cannot be altered after creation. Any modification produces a new list.

#### Recursive Definition

Every list is:

- Empty  
- Head + Tail

This makes recursion natural and essential.<br><br>

#### Homogeneous Data Type

All elements must be the same type:

```haskell
[1,2,3]        -- valid  
['a','b']      -- valid  
[1,'a']        -- invalid
```



### Accessing Head or Tail of Empty List

Calling `head []` or `tail []` causes a runtime error.

---

### Missing Base Case in Recursion

Recursive functions must always define a base case, usually the empty list.

---

### Confusing Head and Tail

- Head = element
- Tail = list

---

#### Efficiency

Prepending (`:`) is efficient.  
Appending (`++`) is less efficient.
