<br><br>

# Networks

One computer, not connected to any other computing device is called a 'standalone'

As soon as you connect two or more computers connected together they form a network

All networks fall into two categories:

- LANs (Local area network)
- WANs (Wide area network)


Some advantages of LANs:

- Cheap, less cables required and its over shorter distances
- Security, they're privately owned, updates can be rolled out quick
- Reliable, backups can be quickly used
- Sharing files and resources quickly

- - -

## Network Topologies

Arrangement of the various computing devices which make up a computer network
<br><br>
### Bus topology

An arrangement where nodes are connected in a daisy chain by a single central communications channel. The backbone one. 

There must be terminators at both ends to stop signals from bouncing back and forth


![[Pasted image 20260223141551.png]]


| Advantages<br>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                       | Disagvantages                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| - It is the easiest network topology for linearly connecting peripherals or computers.<br><br>- It works very efficiently well when there is a small network.<br><br>- The length of cable required is less than a star topology.<br><br>- It is easy to connect or remove devices in this network without affecting any other device.<br><br>- Very cost-effective as compared to other network topology i.e. mesh and star<br><br>- It is easy to understand topology.<br><br>- Easy to expand by joining the two cables together. | - Bus topology is not good for large networks.<br><br>- Identification of problems becomes difficult if the whole network goes down.<br><br>- Troubleshooting individual device issues is very hard.<br><br>- Need terminators are required at both ends of the main cable.<br><br>- Additional devices slow the network down.<br><br>- If the main cable is damaged, the whole network fails or splits into two.<br><br>- Packet loss is high.<br><br>- This network topology is very slow as compared to other [**topologies**](https://www.geeksforgeeks.org/computer-networks/types-of-network-topology/ "https://www.geeksforgeeks.org/computer-networks/types-of-network-topology/").<br><br>- Bad security as all nodes have access to the data being sent over the network |

**Operation of a bus network:**

- All nodes are connected to a single backbone cable
- Each end of the backbone is connected either to a terminator or a computer to prevent signals  from 'bouncing back'
- Each node is passive
- Data is sent one direction at a time only
- only one computer can transmit successfully at one time
	- CSMA/CD tech is used to enable the nodes to transmit data on the same cable


- - -

### Star topology

An arrangement where a central node or hub provides a common connection hub to all nodes


![[Pasted image 20260223142855.png]]


| Advantages                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                 | Disadvantages                                                                                                                                                                                                                                                                             |
| -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| - If N devices are connected to each other in a star topology, then the number of cables required to connect them is N. So, it is easy to set up.<br><br>- Each device requires only 1 port i.e. to connect to the hub, therefore the total number of ports required is N.<br><br>- It is Robust. If one link fails only that link will affect and not other than that.<br><br>- Easy to fault identification and fault isolation.<br><br>- Star topology is cost-effective as it uses inexpensive coaxial cable.<br><br>- New devices can be added without disruption<br> | - If the concentrator/connecting hub device on which the whole topology relies fails, the whole system will crash down.<br><br>- The cost of installation is high.<br><br>- Performance is based on the single concentrator i.e. hub.<br><br>- Requires more cables than bus topology<br> |


**Operation of a star network:**

Computers are connected to a central node, This is often either a switch or a hub

- A **Switch** send each communication to the specific computer it is intended for
- A **Hub** broadcasts the message to every computer on the LAN

- - -

### Peer-to-peer Architecture

- A peer-to-peer network has no central server

![[Pasted image 20260224120105.png]]


Features of a peer-to-peer network include:
- Suitable for small companies with fewer computers
- No central server controls files or security
- All computers can easily see the files on all other computers
- All computers can communicate with each other without going through a server
- If a computer is switched off, data cannot be retrieved<br><br><br>

**Peer-to-peer on a WAN**

The P2P configuration can also be used for file-sharing websites
BBC iPlayer uses P2P networking
	- This means that with thousands of people downloading, data can be passed between computers rather than just from the server
Often used for illegal distribution of copyright material as they're very difficult to shut down<br><br><br>

**Peer-to-peer file sharing**

A file request can return several parts of the same file from multiple copies on multiple computers<br><br><br>

**The issue with peer-to-peer networking**

Websites may go down because by this<br><br><br>


**Architecture Summary**


|Client Server|Peer-to-peer|
| --- | --- |
|  User Ids,passwords and access levels centrally controlled   |  Files and programs stored on individual computers   |
| Used in many small , medium size and large organisations | Suitable for a home computer network |
| Can be expensive to set up and to manage | Cheap to set up and maintain |
| Backup is centralised and usually automated | Each computer on the network can act as both client and server |
| No access to other users files | Can be used for sharing of music and streaming coverage of live events |


---



## Carrier Sense Multiple Access<br><br>

CSMA with Collision detection (CSMA/CD) detects two nodes attempting to transmit simultaneously

- Both nodes cease transmission and wait a random mount of time before reattempting 

- CSMA with collision avoidance (CSMA/CA) is used with wireless networks<br><br>


- - - 
  
## MAC Addressing<br><br>

Every network device contains a Network Interface Card (NIC)

Each NIC is attributed a unique Media Access Control (MAC) address hard coded in manufacture

- A switch holds all of the MAC addresses for each device connected to it and uses these to direct packets of data to the correct device


| Advantages                                                                                                                            | Disadvantages                                                                                                      |
| ------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------ |
| - Easy to isolate problems<br><br>- Good performance<br><br>More secure if a switch is used as data is sent only to the recipient<br> | - Can be expensive to set up because of the length of cable required<br><br>- Central device is a point of failure |


- - - 

## Physical vs Logical topology

The **physical** topology of a network defines how the devices are physically connected

The **logical** topology defines how the devices communicate across he physical topologies

-  A network wired in star topology can behave logically as a bus network by using a bus protocol and appropriate physical switching
  
  

- - - 

## Cloud computing

'The cloud' is simply an imaginative term for internet computing, using remote servers run by organisations such as Dropbox, Microsoft, or thousands of other specialist software companies<br><br>

**Advantages of Cloud computing**

1. Some software does not have to be downloaded to the users computer. All the software and data files are held by the software manufacturer 'in the cloud'<br><br>
2. Software and data is accessible from any computer anywhere in the world<br><br>
3. The data is automatically backed up so there is no danger of losing it<br><br>
4. The software and data does not occupy space on the users hard drive<br><br>
   
