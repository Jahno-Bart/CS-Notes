# Communication Methods

## How devices communicate

Communication relies on transmitting and receiving data in the form of electromagnetic signals

Within a computer system, data is represented as a series of electrical voltages: a high voltage represents a logical 1, and a low voltage represents a logical 0. These 1s and 0s are the binary digits (i.e. bits) that represent all of the information that a computer can store and transmit.

In wired communication between devices, the signal would be a sequence of voltages or light pulses that travel through a cable.

In wireless communication, the signal would consist of radio waves. In both cases, what is transmitted is a sequence (or stream) of bits.

----------

## Synchronous and asynchronous transmission

**Synchronous transmission**
- In synchronous transmission, streams of bits are transferred over a communication channel at a constant rate. The transmitter and the receiver are synchronised using a common clock signal.

**Asynchronous transmission**
- In asynchronous transmission, there is no clock signal, so additional data (start and stop bits) is used to control the communication. Data is transmitted when it is available, rather than at specific intervals. This means that there can be periods of time when the transmission channel is idle.

<br><br>


| Feature | Asynchronous Transmission | Synchronous Transmission |
|-------|--------------------------|--------------------------|
| Timing control | Sender and receiver are not continuously synchronised | Sender and receiver are kept in sync by a clock signal |
| Start/stop bits | Uses start and stop bits to mark each transmission | No start or stop bits needed |
| How synchronisation is achieved | Receiver uses the start bit to prepare and the stop bit to reset | Both sender and receiver use the same clock signal |
| Efficiency | Less efficient due to extra start and stop bits | More efficient – more data sent per unit time |
| Data rate | Slower | Faster |
| Typical use | Serial data transmission where timing may vary | Commonly used with parallel transmission |
| Example | Serial communication | Inside a computer (address, data, and control buses) |


----------

## Serial and parallel transmission

**Serial transmission**
- In serial transmission, data bits are sent in a sequence, one after the other, over a single line.

**Parallel transmission**
- In parallel transmission, several bits are sent at the same time over a set of parallel lines. This type of transmission is only reliable over short distances, so it is mainly used inside a computer and in some early peripherals. The parallel connections used are known as 'buses' and are typically 8, 16, or 32 lines wide.

<br><br>


| Feature | Parallel Transmission | Serial Transmission |
|-------|----------------------|--------------------|
| How data is sent | Multiple bits sent at the same time over multiple wires | Bits sent one at a time over a single wire |
| Suitable distance | Short distances only | Can transmit over long distances |
| Bit rate | Lower effective bit rates over distance | Can operate efficiently at high bit rates |
| Skew | Affected by skew (bits arrive at different times) | Not affected by skew |
| Crosstalk | More susceptible due to many wires close together | Less susceptible due to fewer wires |
| Reliability | Data may become corrupted and need re-sending | More reliable over long distances |
| Cost | More expensive due to more wires and pins | Cheaper to implement |
| Physical size | Requires more space and infrastructure | Uses fewer wires, takes up less space |
| Interfaces | Older parallel interfaces | Modern interfaces (e.g. USB) |
| Example use | Short internal connections | Peripherals, long-distance communication, fibre optics |


----------

Communication between devices can be described as simplex, half-duplex, or full-duplex, depending on the direction data can travel.

**Simplex transmission**
- Simplex transmission is one-way only, with data sent from a sender to a receiver and no return path. A common example is a TV remote using infrared, where signals go from the remote to the TV.

**Half-duplex**
- Half-duplex transmission allows data to travel in both directions, but not at the same time. Devices take turns using the communication channel. Walkie-talkies are an example, where one user speaks while the other listens.

**Full-duplex**
- Full-duplex transmission allows data to travel in both directions at the same time. This requires two channels or technology that allows two signals to share the same medium without interference. Internet cables and telephones are examples.

**Relationship**
Simplex, half-duplex, and full-duplex transmission can all be used with serial or parallel communication. For example, the connection between a processor and main memory is often half-duplex parallel, as data is either read or written at one time and the distance is short.


----------

## Multiplexing

**Multiplexing** is a technique that allows multiple signals to be transmitted at the same time over a single communication link by combining them into one complex signal. A multiplexer (mux) combines the signals at the sending end, and a demultiplexer (demux) separates them at the receiving end.

In time division multiplexing (TDM), the communication channel is divided into fixed-length time slots, with each device assigned one slot per cycle. If a device has no data to send, its slot remains empty, which can waste bandwidth.

Statistical time division multiplexing (STDM) improves efficiency by only assigning time slots to devices that are ready to transmit. This reduces unused slots and improves channel utilisation.

In frequency division multiplexing (FDM), each signal is transmitted using a different frequency range within the same bandwidth. These frequency ranges do not overlap and are often separated by small unused gaps to reduce interference.

----------

## Switching

Switching is used in networks with multiple possible paths to route data from a source to a destination. In large networks such as the internet, some paths may be unavailable due to faults or maintenance, so alternative routes must be used.

Early telephone systems used manual switching, where operators physically connected callers via a switchboard. Modern digital networks use automated switching with no human involvement.

There are two main switching techniques: circuit switching and packet switching.

Circuit switching establishes a dedicated circuit (route) between the source and destination before transmission begins. All data packets travel along the same route, in order, and the circuit remains reserved for the entire communication session. If part of the circuit fails, a new route must be established. Circuit switching can be inefficient if the reserved bandwidth is not fully used.

Packet switching sends data as individual packets, which may take different routes to the destination and may arrive out of order or not at all. Each packet consists of a header and a payload. The header contains a sequence number, allowing the receiving device to reorder packets and detect any missing packets.

