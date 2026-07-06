First a **network protocol** is a set of rules that lets computers communicate and exchange data over a network. It ensures different devices and systems can understand each other, even if they use different hardware or software.

Now the **OSI model (Open Systems Interconnection model)** is a framework that standardizes how different computer systems communicate over a network. It divides networking into **7 layers**, making it easier for devices and systems to understand and interact with each other.
![[Pasted image 20260706112744.png|521]]
**7 layers of the OSI Model**

  The **Application Layer (Layer 7)** is the top layer of the OSI model. It directly supports user applications like web browsers and email clients by providing the protocols they use to communicate. It handles data formatting and communication rules, such as **HTTP** for web browsing and **SMTP** for email.

  The **Presentation Layer (Layer 6)** prepares data for the application layer by handling **translation, encryption, and compression**. It ensures data is readable by converting formats between systems, encrypts data for secure communication, and compresses it to improve transmission speed and efficiency.
  
  The **Session Layer (Layer 5)** manages communication sessions between two devices. It **opens, maintains, and closes connections**, ensuring data exchange happens smoothly. It also adds **checkpoints** so interrupted transfers can resume from the last saved point instead of starting over.
  
  The **Transport Layer (Layer 4)** provides end-to-end communication between devices. It breaks data into **segments**, manages **flow control and error checking**, and ensures data is delivered correctly. It uses protocols like **TCP** (reliable delivery) and **UDP** (faster but less reliable).
  **IP (Internet Protocol)** provides addressing and routes data packets to the correct device, but doesn’t ensure delivery order or reliability.
  **TCP (Transmission Control Protocol)** works with IP to make communication reliable by **ordering packets, checking for errors, and retransmitting missing data**. It also establishes a connection using a **3-way handshake (SYN, SYN-ACK, ACK)** before data transfer. **UDP (User Datagram Protocol)** is a fast but unreliable transport protocol that sends data without setting up a connection first. It simply sends packets (datagrams) to the destination without checking order, delivery, or errors. Because of this, UDP is faster than TCP, but packets can be lost or arrive out of order. It’s used for real-time applications like video streaming, online gaming, VoIP calls, and DNS lookups.
  
  The **Network Layer (Layer 3)** moves data between different networks. It takes segments from the transport layer, breaks them into **packets**, and routes them to the correct destination using the best path. It also reassembles packets at the receiving end. Key protocols include **IP**, **ICMP**, **IGMP**, and **IPsec**. **Network routing** is the process of finding the best path for data packets to travel across networks from source to destination. It is done by **routers**, which use **routing tables** to decide where to send packets based on their destination IP address. Routes can be **static (manually set)** or **dynamic (automatically updated for best performance)**.
  
  The **Data Link Layer (Layer 2)** handles communication between devices on the **same network**. It takes packets from the network layer and breaks them into **frames** for transmission. It also manages **error detection and flow control** within a local network to ensure reliable delivery between directly connected devices.
  
  The **Physical Layer (Layer 1)** deals with the actual hardware used to transmit data, like cables and switches. It converts data into a **bit stream (0s and 1s)** and defines how signals are sent and interpreted so both devices can correctly read the data.
  Flow - **Data flow in OSI model (simple):**
	On the **sender’s side**, data moves **top → bottom (Layer 7 to Layer 1)** where it is prepared step by step (formatted, segmented, packeted, framed, and converted into bits for transmission).
	On the **receiver’s side**, data moves **bottom → top (Layer 1 to Layer 7)** where it is rebuilt step by step (bits → frames → packets → segments → data → readable message).
	In short: **Sender = data gets broken down for sending, Receiver = data gets rebuilt for reading.**

