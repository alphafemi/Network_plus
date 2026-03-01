The OSI Model Explained
The OSI (Open Systems Interconnection) Model is a conceptual framework used by IT professionals to describe how data moves across a network. It provides a universal language for discussing network operations, making it easier for professionals to communicate regardless of their organization or specific technologies.

What is the OSI Model?
The OSI model describes the process that data takes as it traverses networks. It is not a detailed protocol description but rather provides a broad overview of how data moves through systems.

Most protocols used today are based on TCP/IP, but the OSI model can be applied to many different protocols and works perfectly with TCP/IP. There might be tens or even hundreds of protocols that operate at an individual layer of the OSI model.

By understanding this model, IT professionals can converse with each other in a way that everyone understands. When you mention OSI layer 7 or layer 4, everyone knows exactly what you mean and what effect it has on the overall operation of the network.

The Seven Layers of the OSI Model
If we start at the top of the OSI layer and work our way down to layer 1, we have:

Layer 7: Application Layer

Layer 6: Presentation Layer

Layer 5: Session Layer

Layer 4: Transport Layer

Layer 3: Network Layer

Layer 2: Data Link Layer

Layer 1: Physical Layer

A helpful mnemonic to remember these layers from top to bottom is: "All People Seem To Need Data Processing." This stands for Application, Presentation, Session, Transport, Network, Data Link, and Physical.

Layer 1: Physical Layer
We start at the bottom of the OSI model with layer 1, which is called the physical layer. This layer describes the physical signals that we send through cables and fibers on our network. At this layer, we are really just talking about getting a signal from one part of the network to another.

When we refer to a physical layer problem with the network, we are referring to issues such as a bad cable, a bad fiber, or interference on a wireless network. Troubleshooting at this layer involves running loopback tests, testing cables and fibers, and checking different adapter cards and other devices to make sure they are working properly on the network.

Examples of physical layer components include Ethernet cables like Cat5e, Cat6, or Cat6a, fiber optic connections using single-mode or multi-mode fiber, wireless signals for Wi-Fi and Bluetooth, and connectors like RJ-45, LC, and SC.

Layer 2: Data Link Layer
One step up from the physical layer is layer 2, the data link layer. This is the fundamental layer used to communicate between two devices on the network. We often refer to this as the MAC address layer because it is commonly associated with the network cards in our devices, whether they are Ethernet adapters or wireless adapters.

The physical address on a device is called the data link control address or MAC address. MAC stands for Media Access Control, not the Apple computer operating system. Any time you hear someone talk about a MAC address, they are referring to the hardware address of that particular adapter card.

Since network switches forward traffic based on the destination MAC address, this is a layer that we often refer to as the switching layer. When we refer to a MAC address, a problem with a switch being able to operate, or anything associated with a hardware address, we are referring to OSI layer 2.

A MAC address is a twelve-character hexadecimal number split into pairs and separated by colons, such as aa:bb:cc:dd:ee:ff. The first six characters represent the manufacturer of the network interface, and the last six characters form a unique identifier for that specific device.

Layer 3: Network Layer
The next layer up is OSI layer 3, the network layer. We often call this the routing layer because this is the layer that routers use to determine how to forward traffic. Routers look at the destination IP address to determine what the next hop might be for traffic traversing the network.

This is also the layer where we can fragment frames into multiple pieces, especially when sending data across a network that may require smaller frames than what is used on our local network. We can cut those frames into smaller pieces to fit them through the network and then put those pieces back together on the other side.

Anytime we are referring to a problem relating to IP addressing, subnet masks, or anything about routing, we are probably referring to layer 3, the network layer. IP addresses, subnet masks, and the way routers forward traffic all happen at this layer.

Layer 4: Transport Layer
Layer 4 is the transport layer. As the name implies, this layer is responsible for transporting information from one device to another. You might also refer to this as the post office layer because it is responsible for getting your information from one side of the network to the other.

The protocols that operate at layer 4 are TCP, which stands for Transmission Control Protocol, and UDP, which stands for User Datagram Protocol. These two protocols are commonly responsible for getting all of the information within our IP packets from one device to another. This often involves taking a large amount of data, putting it into smaller pieces to get it across the network, and then putting those pieces back together on the other side.

TCP is connection-oriented and provides reliable, ordered, and error-checked delivery. It is used for web browsing, email, and file transfer. UDP is connectionless and provides fast delivery without error checking. It is used for video streaming, gaming, and DNS queries.

Layer 5: Session Layer
Before we can send information from one side of the network to the other, we may need to create a session so that a device is able to receive that data. Layer 5 is the session layer, and it provides communication management between point A and point B.

Anything relating to the initiation of a session, stopping the session, or restarting the session is associated with the session layer. If an application is using some type of control protocol or tunneling information within existing data, then we are probably using OSI layer 5.

Real-world examples of session layer operations include VPN tunnel establishment, remote access connections, and RPC or Remote Procedure Call.

Layer 6: Presentation Layer
OSI layer 6 is responsible for putting all of this data into a format that we will eventually see with our human eyes. This refers to character encoding, application encryption and decryption, and it is often combined and discussed with the application layer at layer 7.

The presentation layer is the layer that is commonly in operation just before we see data on our screen. We often associate the encryption of application data with this layer. If we are communicating with a website and using SSL or TLS to encrypt and decrypt data, that process is occurring at layer 6.

Examples of presentation layer functions include SSL/TLS encryption for HTTPS connections, character encoding such as ASCII and UTF-8, and data compression using algorithms like GZIP.

Layer 7: Application Layer
The top layer of the OSI model is OSI layer 7, the application layer. This is the layer that we see on our screen. Anytime we are interacting with an application, we are operating at layer 7 of the OSI model.

Common applications that operate at this layer include HTTP and HTTPS for web browsing, FTP for file transfer, DNS for domain name resolution, POP3 and IMAP for email retrieval, and SMTP for sending email. There are thousands of other application protocols that operate at this layer.

Anytime we are seeing something on the screen, interacting with an application, or receiving messages from an application, that is layer 7 information.

      How Data Moves Through the Layers
Here's what happens when you visit a website:

*You type a website address (Layer 7)
*Your browser encrypts the connection (Layer 6)
*Your computer sets up a connection to the server (Layer 5)
*The data gets broken into small pieces (Layer 4)
*Your router figures out where the website server is (Layer 3)
*Your switch sends the data to your router using your MAC address (Layer 2)
*The data travels through cables or Wi-Fi (Layer 1)
On the receiving end, the process happens in reverse—data starts at Layer 1 and works its way up to Layer 7.
