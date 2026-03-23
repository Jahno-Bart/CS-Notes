# Internet

**What is the internet?**
The internet is a global system of interconnected computer networks. The internet facilitates a wide range of services, including the World Wide Web, email, internet telephony, and file sharing. In order to communicate to do any of those things, computers must use a common set of protocols referred to as the TCP/IP stack.<br><br>


## Structure of the internet

- The Internet is a collection of interconnected networks.
- Computers join local networks (LANs).
- These LANs link up with ISPs.
- ISPs connect to the main network paths.
- Talking happens using set rules (TCP/IP).


- People connect to the internet using devices linked by:
    - Wireless connections (Wi‑Fi, mobile data)
    - Wired connections (cables, fibre)
- These connections feed into high‑speed telecommunication networks that span the world.  

**The Internet Backbone**
- The backbone is a mesh of ultra‑fast fibre‑optic cables and powerful industrial routers.
- It moves data extremely quickly across continents.
- Large telecommunications companies build and maintain most of this backbone.
- These companies:
    - Don’t charge each other for using the backbone.
    - Aren’t responsible for guaranteeing its availability or reliability.  

----------

## Connecting to the internet
Your devices connect to your home hub, the hub sends your data through your ISP, and the ISP connects you to the global internet.  

Individuals and organisations access the internet through an Internet Service Provider (ISP). Your connection type depends on what your ISP offers:
- ADSL – uses your telephone line
- Fibre‑optic – a dedicated high‑speed cable
- 3G/4G/5G – mobile network connection if no cables reach your home
- Satellite – used in remote areas with no ground networks  
  
Your ISP provides a device (often called a home hub or router) that links your home network to the wider internet.
This device usually includes:
- Ethernet switch – a few ports for wired devices
- Wireless access point – provides Wi‑Fi
- Router – manages traffic going in and out of your home
- Modem – converts signals so they can travel over your connection type (sometimes built into the router)

<br><br>

![[Pasted image 20260226084308.png]]

<br><br>

Your mobile phone can switch between different networks without you really noticing. At home, it connects through your Wi‑Fi. At school or college, it joins their local network. When you’re out and about, it can access the internet through nearby mobile phone masts.
The connection from your home router to the internet is part of a larger network owned by your ISP. This network might cover just a town or stretch across many miles to reach rural areas, supporting anywhere from a few hundred to several thousand users.
When routers link multiple local area networks (LANs) together, the result is a wide area network (WAN). A company with several offices across a city would also be using a WAN. In the past, companies in the UK often relied on BT “leased lines,” which provided a dedicated, high‑quality connection with guaranteed bandwidth and low latency.
Today, many organisations instead connect their offices over the internet using a virtual private network (VPN). A VPN creates a secure, encrypted link across public networks, allowing devices to communicate as if they were on the same private network, while significantly reducing costs.

<br><br>

![[Pasted image 20260226084324.png]]

<br><br>



## IP Address

- Number code used for directing traffic.

## Domain Structure

- Organized by level of importance.
- From right to left reading order.
- TLD → Domain → Subdomain.
<br><br>
- - - 

## DNS

- Turns names people read into numerical spots.
- A system spread out everywhere.
- Needed for finding the correct servers.

- **Purpose**: 
	- Translates human-readable domain names (e.g., `www.bbc.co.uk`) into machine-readable IP addresses (e.g., `212.58.246.10`) to enable network communication.
- **Process**: 
	- Client → DNS resolver → root server → TLD server → authoritative server → IP returned → cached locally for efficiency.
- **Key Terms**: 
	- DNS resolver, root server, TLD server, authoritative server, caching, IP address mapping.

Practice Question:
	A student is setting up a small computer network in their house. The network will link together the laptops, desktop computers and mobile devices that belong to the people who live in the house.
	When a person in the house uses the network to load a web-page it is likely that the Domain Name Server system will be used.
	Describe the main purpose of the DNS system and how it works

	A DNS turns domain names people read into IP addresses (1) so devices can find websites. It does this by requesting a heirarchy of servers (1) to resolve the name. The result is cached to make it faster in the future.

	Extra points:
	DNS stores a database of FQDNs and corresponding IP addresses
	DNS is a distributed database of mappings
	
<br><br>
- - -

## Internet Registries

- Hand out the IP numbering systems.
- Manage the naming directory system.
- Make sure everything worldwide is unique.
- Keep the Internet operating smoothly.
<br>
- - -
## TCP/IP Layers

- **Application Layer** - Provides network services directly to user applications and handles protocols like HTTP, FTP, SMTP, and DNS for end-user communication.

-  **Transport Layer** - Manages end-to-end communication between applications using protocols like TCP (reliable) and UDP (unreliable), and handles port-based communication.

- **Network Layer** - Handles routing of data packets across networks using IP addresses, with protocols like IPv4, IPv6, and ICMP for logical addressing and routing.

- **Link Layer** (Network Access Layer) - Deals with the physical transmission of data over network hardware using MAC addresses, handles frame formatting, and manages hardware addressing.<br><br>

```
In 300 words or fewer
When sending data across a network, explain how the TCP/IP stack is used

When data is sent across a network it passes throught the TCP/IP stack layers with each layer adding its own information. It starts at the application layer where the user apllication prepares data and passes it into the transport layer specifying which protocol to use. The transport layer breaks it down into segments adds a header containing source and destination port numbers as well as sequence numbers to help in rebuilding the data, this is then pased on to the network layer. The network layer then adds another header containing source and destination IP addresses and time to live, creating a packet, To prevent the packet from bouncing around it give a 'Time to live'. This layer uses routing protocols to determine the best path for the packet to reach its destination. The packet is then passed on to the link layer which adds a frame header containing source and destination MAC addressess creating a frame. This layer handles the physical transmission of the frame over the network medium. The frame is converted into electrical signals and transmitted. At the recieving end this is reversed.
```

### Packet switching
**Packet switching** is a method of transmitting data across a network by breaking it into smaller units called **packets**. Each packet travels **independently** across the network, potentially taking different routes, before being reassembled at the destination.

#### Advantages of Packet Switching (TCP/IP)

- **Efficient use of bandwidth**: Multiple data streams can share the same network path simultaneously.
- **Fault tolerance**: If one route fails, packets can be rerouted dynamically via other paths (thanks to IP routing).
- **Scalability**: Easily supports large, complex networks like the Internet.
- **Cost-effective**: No need to reserve dedicated circuits for each connection.

#### Disadvantages of Packet Switching (TCP/IP)

- **Variable latency**: Packets may take different routes, causing delays or out-of-order delivery (TCP must reorder them).
- **Overhead**: Each packet requires a header (IP + TCP), increasing total data transmitted.
- **Collisions**


#### What devices needed when we have to change protocols?

A **gateway** is required


#### Protocols

- **FTP** – Transfers files between client and server (ports 20/21), but lacks encryption.
- **HTTP** – Delivers web content over port 80; unencrypted and stateless.
- **HTTPS** – Secure version of HTTP (port 443) using SSL/TLS encryption for safe web browsing.
- **POP3** – Downloads emails to a local device (port 110), usually deletes them from the server.
- **SMTP** – Sends outgoing emails (port 25) from client to mail server.
- **SSH** – Secure remote access and command execution (port 22), also supports encrypted file transfer uses asymmetric encryption.

#### Socket

- A mix of the IP address and a specific line number.
- Points to one exact program on a machine.
- Lets one running task talk to another.

A socket is an endpoint for network communication that **combines an IP address and a port number**. It represents one end of a network connection and is used by applications to send and receive data across a network. Sockets operate at the transport layer and can use either TCP (connection-oriented) or UDP (connection-less) protocols. A socket is identified by a unique combination of IP address and port number, allowing multiple applications to communicate simultaneously on the same device. Sockets enable bidirectional communication between client and server applications over a network.

#### MAC Address

- A unique identifier built into the hardware.
- Employed inside a local network.
- Functions at the Link layer.
- IP addresses are logical; MAC addresses are physical.

A MAC (Media Access Control) address is a 48-bit hardware identifier unique to a network interface card (NIC) on a device. It is expressed in hexadecimal format as six pairs of characters, separated by colons (e.g., 00:1A:2B:3C:4D:5E). MAC addresses operate at the Link Layer and are used for communication within the same local network segment (LAN). They are used by protocols like ARP (Address Resolution Protocol) to map IP addresses to physical hardware addresses. MAC addresses are only relevant for devices on the same physical network and are not routed across the internet.

#### Well-Known Ports

- The range is 0–1023.
- Set aside for widespread services for example:

|Port|Use|
|---|---|
|20|FTP Data Transfer (File Transfer Protocol - data channel)|
|21|FTP Control (File Transfer Protocol - command channel)|
|22|SSH (Secure Shell - secure remote access and file transfer)|
|80|HTTP (HyperText Transfer Protocol - unencrypted web traffic)|
|143|IMAP (Internet Message Access Protocol - email retrieval)|
|443|HTTPS (HyperText Transfer Protocol Secure - encrypted web traffic)|

#### Ephemeral Ports

- Short-lived ports for clients.
- Utilized for getting replies from servers.
<br><br>
- - -


## Worms vs Viruses vs Trojans

#### Worms

Self-replicating programs that spread independently across networks without user action. They exploit security vulnerabilities and consume bandwidth, causing system slowdown.

#### Viruses

Malicious code requiring user action to execute (opening infected files). They attach to host programs, replicate when executed, and can corrupt data or steal information.

#### Trojans

Disguised as legitimate software but contain hidden malicious code. They don't self-replicate; users must download them. They create backdoors for unauthorized access or steal data.

**Key Difference:** Worms spread autonomously; viruses need user interaction; trojans rely on deception.

```
Practice Question:
In 50 words or fewer explain the key characteristics of each of these types of malware (Worms, viruses, trojans) ensuring that the differences between them are clearly highlighted

A worm is a program which self replicates that spreads accross networks without user action. A virus is malicious code which requires a user to exectute. They attach to host programs and replicate when executed and can corrupt data. A trojan is a legitimate software disguise on malicious code, its not self replicating and a user must download it, they create backdoors.
The main difference is worms spread on their own, viruses require user execution and trojans depend on deception.
```


## How to protect against threats

- Keep all software up to date
- Anti-malware software
- Firewalls
- Education on training against social engineering
- Strong password rules
	- 2FA
- User access levels
<br><br>

- - -


## Digital Signature

A **digital signature** is a cryptographic technique used to verify the authenticity and integrity of a message or document. It ensures that the message was sent by the claimed sender and hasn’t been altered in transit.

1. As the sender
	1. write your message
	2. Hash the message
	3. Encrypt the hash using the senders private key
	4. Add this encrypted hash to the end of my message
	5. Encrypt the entire thing (message + encrypted hash) using receivers public key
	6. Send the message

2. As the receiver
	1. Decrypt the hash using the senders public key
	2. Hash the decrypted message using same algorithm
	3. Decrypt the signature
	4. Compare the two hashes, if they match then the signature is real
<br><br>

## Digital Certificate

when the sender digitally signs a message, they also send their digital certificate
A trusted company is know as a Certificate Authority (CA) provides this, which includes:
- A serial number
- Name of the CA
- Expiry date
- Subject (name of the holder)
- Subjects public key
- CAs digital signature of the certificate to verify the certificates origin and integrity

- - -

### Accessing Web pages

- The web-page has to GET all the code from the HTML, CSS, JavaScript and PHP or python
- The web-page then builds a Document Object Model
- Gets any videos or images from the server
- Renders the web page
- Then executes the code

- - -