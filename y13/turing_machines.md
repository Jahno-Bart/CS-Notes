## Turing Machines

### Components of a Turing Machine

There a various necessary components:

- A infinitely long tape divided into squares
- A finite alphabet of symbols, e.g {0,1}, the set of binary digits
- A sensing read/write head: this would be able to look at a square on the tape and read its symbol. In response to what was read, the machine could leave the symbol unchanged, or replace it with another symbol (including erasing the symbol to leave the cell blank). The head would then move left or right one square at a time.
- A finites set of states: one state is the start state and there would be one or more hating states (with no outgoing transitions)
- A set of transition rules: to specify how the machine operates
<br><br>

### The transition rules

The rules are expressed in the form of a **transition function**. By convention the Greek letter 'delta' ( δ ) is used to represent the transition function, which is written in the form:

**δ (Current state, input symbol) = (new state, output symbol, movement)**
<br><br>
Thus the rule δ (S0, 0) = (S3, 1, <-) would be read as follows:

**IF** the machine is currently in state 0 (S0) **AND** the input symbol is 0, **THEN** the machine will transition to state 3 (S3), write a 1 to the tape and move a cell to the left
<br><br>

#### A Turing machine models a single fixed program

A Turing machine can be viewed as a computer with a single fixed program. For each program, a separate machine would be needed. This seems like a strange concept in today's world, but at the time, computing machines were built with the components and architecture to solve just one specific problem. Turing's work proved that computers did not need to be different.

<br><br>

#### Relationship between a Turing machine and a modern computer

The memory on the Turing machine is the infinitely long tape. Data is stored and modified by writing to the tape. The transition function provides the program to be executed.
<br><br>

### Relationship between transition function and state transition diagram




