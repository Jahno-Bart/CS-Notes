# The components of the processor

### Central Processing Unit (CPU)
The CPU is responsible for executing instructions and consists of:
- **Control Unit (CU)** – directs all operations and manages data flow
- **Arithmetic Logic Unit (ALU)** – performs arithmetic and logical operations
- **Registers** – small, fast storage locations used during instruction execution

### Main Memory (RAM)
- Stores both **instructions** and **data**
- Organised as a table of **addresses** and **data values**

### System Buses
Data is transferred between CPU and RAM using three buses:
- **Address Bus**: carries the address of the memory location being accessed (one-way)
- **Data Bus**: carries data and instructions between CPU and memory (two-way)
- **Control Bus**: carries control signals (e.g. read, write, interrupt)

### Control Unit

The **control unit** organises the sequence of micro-operations that need to be performed in order to carry out an instruction

The control unit is responsible for the following tasks:

- Decodes every instruction to determine what needs to be done (for example, perform an arithmetic calculation, a logic operation, or load data from main memory)
- Sends and receives control signals to and from other components (for example to enable data to be read (i.e. loaded) from and written (i.e. stored) to the main memory)
- Checks that signals have been delivered successfully
- Makes sure that data goes to the correct place at the correct time
- Ensures the execution of instructions in the correct sequence

The control unit receives a signal from the clock that is used to synchronise operations

### Arithmetic and Logic Unit (ALU)

The **arithmetic and logic unit** is responsible for performing arithmetic calculations and logical operations that include:

- Addition, Subtraction, Multiplication, Division
- Logical bitwise operations such as AND, OR, NOT and XOR
- Comparisons between values such as greater than, less than, equal to
- Shifting binary patterns to the left or right


### Registers

**Registers** are locations of very high speed computer memory **within the processor**.

**General-purpose registers** are used to store the results of the intermediate calculations that are part of larger computations.

- Used for temporary storage of data and addresses
- Faster access than RAM

**Dedicated or special-purpose registers** have a specific purpose within the fetch-decode-execute cycle. Their roles are specified below:

| **Register** | **Purpose** |
| -------------- | --------------- |
| Program Counter (PC) | Holds the address of the next instruction to be executed by the processor |
| Current instruction register (CIR) | Holds the instruction that the processor is currently executing |
| Memory address register (MAR) | Holds the address of the memory location (in main memory) that the processor needs to access, either to read from (i.e. load data) or write (i.e. store data) to. |
| Memory buffer register (MBR) | Holds the data (data values or instructions) that are read from or written to the main memory. |
| Accumulator (ACC) | Stores the result of any calculation processed bu the ALU |
| Status register (SR) | Stores information about the result of the last instruction that the ALU executed. Each bit within the status register acts as a flag to indicate if an error or exception has occurred within the process. The SR can also be set to enable or disable interrupts. |


### Clock cycles and processor speed

Every operation of the processor typically requires a number of clock cycles to complete

Consider the requirement to read in data from a main memory location:

- The address of the location to be accessed will be transferred to the memory address register.
- The processor sends a read request via the control bus, along with the address of the memory location via the address bus. These operations can happen at the same time (i.e. in the same clock cycle).
- Depending on how long it takes to access the memory, the processor then receives the contents of that memory location via the data bus.
- The data is stored in the memory buffer register (ready for processing).

This operation will have taken a number of clock cycles.

----------


# The fetch-decode-execute Cycle

The fetch-decode-execute cycle describes the basic operation of modern computer systems.

### The Stages of the cycle

A program cannot be run until the program instructions are loaded into main memory (RAM)


#### Fetch

The instruction is fetched from main memory and stored in the processor. The control unit can then access the instruction so that it can be decoded and executed.

#### Decode

The instruction needs to be decoded before it can be run. This is the process the control unit uses to work out what signals to issue to the other components for the instruction to be executed.

#### Execute

The control unit will send signals to the relevant components so that the instruction is carried out.


### Stored Program Concept

The concept that the program must be transferred to main memory before being run is called the stored program concept.

The machine code instructions that make up each program are loaded and stored in main memory before the program can be run. This allows today's computer systems to run a very wide range of diverse programs.

- The program instructions have been translated into machine code
- The program instructions have been loaded (from secondary storage) into the main memory (RAM). The processor cannot access secondary storage directly.
- Then the program instructions are fetched from the main memory and executed one by one


### Fetch Stage

1. The **PC** holds the address of the next instruction.
2. The contents of the PC are copied into the **MAR**.
3. The address in the MAR is placed onto the **address bus**.
4. The control unit issues a **memory read** signal via the control bus.
5. RAM places the instruction stored at that address onto the **data bus**.
6. The instruction is transferred into the **MBR**.
7. At the same time, the **PC is incremented by 1**:
   - Assumes sequential execution
   - May later be overwritten by branch instructions
8. The instruction is copied from the **MBR** into the **CIR**.

---

### Decode Stage

- The control unit analyses the instruction stored in the **CIR**.
- The instruction is split into:
  - **Opcode** – identifies the operation to be performed
  - **Operand(s)** – identifies data, registers, or memory addresses involved
- During decoding, the control unit may:
  - Determine the instruction type (e.g. arithmetic, data transfer, branch)
  - Fetch additional data from memory if required
  - Initialize or configure registers and flags
  - Prepare the ALU for the required operation
- Appropriate **control signals** are generated to coordinate execution.

---

### Execute Stage

The execute stage varies depending on instruction type:

**Arithmetic and Logic Instructions**
- Operands are fetched from:
  - Registers
  - Accumulator
  - Main memory (if needed)
- The **ALU** performs the calculation or logical comparison.
- The result is stored in:
  - Accumulator
  - A general-purpose register
  - Main memory

**Data Transfer Instructions**
- Data may be:
  - Loaded from memory into a register
  - Stored from a register into memory

**Branch and Control Instructions**
- The instruction may:
  - Modify the **PC** to a new address
  - Enable non-sequential program execution
- Conditional branches depend on **status flags** (e.g. zero, carry, overflow).

---

### Status Register and End-of-Cycle Operations
- After execution, the processor checks the **status register**, which may contain:
  - Arithmetic flags (zero, negative, overflow, carry)
  - Error indicators
  - Interrupt signals
- If an **interrupt** is detected:
  - The current state is saved
  - Control is transferred to the appropriate **interrupt service routine (ISR)**
- Once handled, normal program execution resumes.

