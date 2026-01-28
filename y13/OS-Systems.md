## Operating System

**An operating system is the most fundamental piece of system software**

It manages interactions between software and hardware

It is responsible for a range of functions such as: 

- **managing processor time**
- **memory management**
- **I/O**
- **security**

All other software requires an operating system in place, which will:

- Act as a platform on which the other software can run
- Handle the operations that are common to different pieces of software running on the same system

----------

### OS Processor Management

An OS will use a **scheduler** to swap tasks in and out of the processor.

The scheduling algorithm determines:

- How the processing time will be divided — for example, the processes may not all be allocated the same amount of processing time
- In what order the processes will be allocated processing time — for example, based on the perceived importance of the processes that are running, and how interrupts are handled

When the OS swaps between processes:

- The process that is currently running is paused, its state is saved, and it is moved back into a queue
- The scheduler determines which process needs to run next

This is so that you can use multiple software at once. This is known as **multi-tasking**.



----------

### Memory Management

The instructions and data needed for a process to have to be available in main memory, to ensure this the OS runs a **memory manager** program which:

- Keeps track of what portions of memory have been allocated
- Maps memory to each process
- Determines how much memory to allocate to each process
- Determines when a portion of memory should be available for a process

----------

### File Management and Backing Storage Management

**File management** from a user perspective is UI tool that alllows a user to create, rename, move and delete files and folders.

However behind the scenes, the operating system controls how data is stored and retrieved. The operating system keeps track of where the files are stored on secondary storage so that they can be quickly accessed when requested.

**Backing storage management** refers to any non-volatile memory storage device. The operating system keeps a directory of where files and programs are stored so that they can be accessed quickly when they're requested and transferred into main memory.

Keeping a directory also speeds up storage and saves computational resources, rather than having to search for free space every time a user wants to save a file.

----------

### Management of I/O and Interrupts

The OS manages I/O devices in various ways:

- It records which device requires processor time so that the processor can communicate with the device without any conflicts
- It prioritises processes based on control signals that the I/O device sends and receives

An **Interrupt** is a signal that is sent to the processor to request immediate attention.

When the processor receives this request, it suspends what it is doing and runs the process associated with the interrupt.

The processor can be interrupted for a number of reasons, including:

- A hardware device has signalled that it has data to process
- A hardware device has completed a task that it was asked to do
- A software process needs a service to be provided or OS function to be performed
- An allotted amount of time has expired and an action needs to be performed
- A hardware failure has occurred and needs to be addressed

----------

### Device Drivers

A **device driver** is a program that controls the operation of a specific type of device (e.g. printer, keyboard, mouse, etc.) that is part of a computer system. Manufacturers build hardware devices in different ways — a device driver provides an Interface that allows the operating system to interact with the device, which in turn allows it to interact with the software on your computer.

----------

### Security

Operating systems often include security specific utility software such as:

- Firewalls
- Anti-malware
- Checks for software updates

----------

### User Interfaces

To allow the user to interact with the computer, an operating system provides a user interface (UI). There are various forms that a UI can take.

#### Command line interface (CLI)

A CLI allows the user to interact with the system by typing in specific commands. The user enters in text at a command prompt. It is at this prompt that the user is able to issue commands that are executed by the system.

Requires a low amount of secondary storage and RAM because there are no graphics. 

Some people may also prefer this as it allows greater control

#### Graphical user interface (GUI)

Most common form of operating system found and its usually made up of:

- Windows
- Icons 
- Menus
- Pointer

Considered to be **user-friendly**
