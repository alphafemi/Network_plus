Routers
A router is one of the most common devices you will find in a data center. Its job is to take data on one IP subnet and route that information to a different IP subnet. These subnets might be next to each other in the same data center, or they might be located in different parts of the world.

Routers operate at OSI layer 3, which is the network layer. At this layer, we work with IP addresses, and routers use these IP addresses to determine the next hop for data traveling across the network.

Sometimes you will see routing functionality built into a switch. These are called layer 3 switches. The switch itself is still operating at layer 2, but it also includes layer 3 routing capabilities within the same device.

Routers often connect many different types of networks. You might connect a Local Area Network (LAN) to a Wide Area Network (WAN), and these connections might be copper-based or fiber-based. Routers can have many different interfaces to connect all of these diverse networks together.

Network Switches

Switches operate at the MAC address layer to forward traffic. This makes them OSI layer 2 devices, also known as data link layer devices. Switches operate mostly in hardware, using special chips called ASICs (Application-Specific Integrated Circuits).
Modern enterprise switches have many additional capabilities. For example, many switches support Power Over Ethernet (POE), which allows them to provide power to devices like phones and access points through the same ethernet cable used for data. As mentioned earlier, when a switch includes routing functionality, it is often called a layer 3 switch.

*Firewalls

Security is essential on any network, which is why firewalls are used both at home and in business environments. A traditional firewall filters traffic based on TCP or UDP port numbers. However, modern firewalls, called Next-Generation Firewalls (NGFW), can identify specific applications traversing the network and allow you to control whether those applications are permitted.

Most firewalls include additional functionality beyond basic filtering. One common feature is the ability to create Virtual Private Networks (VPNs). This allows you to create an encrypted tunnel between two firewalls at different locations, securing the data passing between them.

Firewalls can also operate as layer 3 devices, meaning they can act as routers. Since firewalls often sit between the internal network and the internet, they manage all communication between the inside and outside of the network.

Many firewalls also provide Network Address Translation (NAT), which allows multiple devices to share a single public IP address. They also often support dynamic routing protocols to help determine the best path for traffic.

*Intrusion Detection and Prevention Systems

Many data centers have standalone IDS or IPS devices, though much of this functionality is now integrated into next-generation firewalls. IDS stands for Intrusion Detection System, while IPS stands for Intrusion Prevention System.

Both systems work by looking for attacks inbound to your network. They can identify common attack types, such as exploits against operating systems or applications. These attacks might take advantage of known vulnerabilities through buffer overflows, cross-site scripting, or other methods.

The difference between the two is important. An IDS can only alert you when it detects an attack. An IPS goes further and can actually block the attack before it reaches your network. Because an IDS cannot block traffic, intrusion prevention systems are more commonly used in enterprise environments.

*Load Balancers
If you have ever accessed a website used by millions of people, you might wonder how that site stays up and running without downtime. The answer is often a load balancer.

A load balancer distributes traffic across multiple physical servers. As an end user, you may have no idea this is happening. But in the data center, there might be dozens or hundreds of servers working together behind the load balancer.

Load balancers are also excellent at detecting server failures. If one server fails due to hardware or software problems, the load balancer notices immediately, removes that server from the rotation, and continues providing access using the remaining servers.

Load balancers can also optimize communication in several ways. They can perform TCP offloading to speed up connections, handle SSL encryption and decryption (SSL offload) so servers do not have to, cache frequently requested data to respond faster, and prioritize certain types of traffic using Quality of Service (QoS).
Some load balancers can even direct specific web pages to specific servers, which is useful when different content is hosted on different machines.

*Proxies
Organizations often have security concerns about users directly accessing servers or services on the internet. A proxy addresses this by sitting in the middle of the communication between the user and the server.

When a user makes a request, the proxy performs that request on their behalf. It receives the answer, checks it for malicious software or code, and then provides the result to the user. This allows the organization to control and monitor all internet access.

Because the proxy sits in the middle of all communication, it is also an ideal place to cache content. If multiple users request the same web page, the proxy can serve that cached content immediately without accessing the internet again.

Proxies can also provide access control by requiring a username and password, filter URLs to block inappropriate content, and scan for malicious software before it reaches the user.

There are two types of proxies. Explicit proxies require you to configure your operating system or applications to use them. Transparent proxies work invisibly without requiring any configuration on your device.

*Network Storage
Data centers store massive amounts of documents and files on centralized storage facilities. There are two main types of network storage.

--Network-Attached Storage (NAS) provides file-level access. This means that to access information within a file, you must copy the entire file across the network into your system's memory. When you make changes and save, you must write the entire file back to the NAS. This works well for many applications but can be inefficient for large files with small changes.

--Storage Area Network (SAN) provides block-level access, which is more efficient for certain workloads. Instead of copying the entire file to make a small change, you only transfer the specific blocks that were modified. This is much faster when working with very large files where only small portions change.

Whether using NAS or SAN, these storage systems typically have their own isolated network with very high bandwidth to handle the massive amount of data being transferred.

*Wireless Access Points
If you look at the ceiling in an office building, you will likely see a wireless access point. This device allows devices to connect to the network wirelessly.

This is different from the wireless router you might have at home, which combines a router, wireless access point, and switch in one device. In enterprise environments, devices are usually purpose-built for specific functions. An access point handles only wireless communication.

On one side of the access point is the wireless network (using 802.11 standards), and on the other side is an ethernet connection (802.3). The access point bridges these two networks, which is why it is called an OSI layer 2 device, operating at the data link layer.

*Wireless LAN Controllers
In most businesses, you need more than one access point to provide coverage throughout a building or multiple buildings. This creates a challenge: how do you manage all of those access points?

Instead of configuring each access point individually, you can use a wireless LAN controller. This is a centralized management tool that allows you to control all access points from one location.

From this single device, you can deploy new access points with full configurations automatically, monitor performance and security across all access points, make changes to all access points with one click, generate reports on usage patterns to determine if you need additional access points, and manage security settings and access policies for the entire wireless network.
These systems are often proprietary, meaning the access points and controller must come from the same manufacturer.

