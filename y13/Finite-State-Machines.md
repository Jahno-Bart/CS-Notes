### What is it: 

**It is an abstract model of computation that is used to model logic** 

In simpler terms => A finite state machine is a simple, step-by-step model that shows how something changes between a small number of states, depending on its inputs. It’s a way of representing logical behaviour. 

A finite state machine is a machine that can, at any point in time, be in a specific state from a finite set of possible states. It can move to another state by accepting an input. If the machine allows for outputs, it can produce an output. 

The machine can only be in one state at a time 

An FSM which has no output is known as a finite state automaton 
<br><br>
<br><br>
### Diagrams
FSMs are usually drawn as ⬇️ 

 

State Transition Diagrams: With the table you can create this

| State       | Description             |
| ----------- | ----------------------- |
| S0<br>      | Switched off            |
| S1          | On and moving forward   |
| S2          | On and moving backwards |
| **Input**   | **Description**         |
| Button push | On/Off button           |
| Sensor      | Collision sensor        |



The symbols of a state diagram symbols are the following


<br><br>
Some FSMs have a special state called the accepting state (indicated by a double circle). It is reached when a valid string is entered. It is possible for FSMs to have more than one accepting state.

FSMs can also be represented using State Transition Tables:

| Current State | Input | Next State |
| ------------- | ----- | ---------- |
| S0            | 5p    | S1         |
| S0            | 10p   | S2         |
| S0            | 20p   | S4         |
| S1            | 5p    | S2         |
| S1            | 10p   | S3         |
| S1            | 20p   | S0         |
| S2            | 5p    | S3         |
| S2            | 10p   | S4         |
| S2            | 20p   | S0         |
| S3            | 5p    | S3         |
| S3            | 10p   | S0         |
| S3            | 20p   | S0         |

<br><br>
<br><br>

### **Mealy Machines**

Finite state machines that include outputs have specific names. A Mealy machine produces an output that is **determined by its current state and the input**. This means that a particular input might generate a different output, depending on the state at which it is applied. Most digital devices, including computers, are implemented by the logic of this type of finite state machine. It is used in language parsing. Can be used to translate from one language to another. 

To specify an output in a state transition diagram, you need to label the output on the transition and use a vertical bar to separate input and output, as shown below. 


**Regular Language** - a formal language that comprises of a set of strings and These strings are made up of symbols from a defined alphabet. 

**A-Level Definition** = A regular language is a language that can be defined by a regular expression otherwise it's not a regular language


Regular expressions use a compact notation to describe the set of strings that make up a regular language. They are a very precise way of specifying a pattern that applies to all members of the set and are particularly useful when the set has many elements. 

Regular expressions work on the principle of providing characters that must be matched. For example, the regular expression cat would match the consecutive characters c-a-t.


| Metacharacter | Column2 |
| -------------- | --------------- |
| + | One or more of the preceding character |
| * | Zero or more of the preceding character  |
  ? | Zero or one of the preceding character |
| \| | Alternation (whats on left whats on right) |
| () | Defines a group |

#### Examples

------- To be finished ----------


One or more a's and one or more b's  {ab, aab}

zero or more a's follwed by b  {b, ab, aaab, aab}

Zero or one a followed by b or b followed by one or more a's  {ab, b, ba, baa}

One or more ab's {ab, ba}

<br><br>

S = {10, 100, 1000, ...01, 011, 0111}  =  (10)+ | (01)+

S = {10001, 1000, 1011, 10111} =  10(${infinite}|11)|?
