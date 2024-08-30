## Network Segmentation

### Broadcast Domains
- **Definition**: A broadcast domain is a network segment in which if one device sends a broadcast frame, all the devices in the same segment receive it.
- **Purpose**: Segmentation of a network into smaller broadcast domains reduces unnecessary traffic and improves network efficiency.
- **Implementation**: Routers are commonly used to define and separate broadcast domains.

### Routers as Boundaries
- **Function**: Routers operate at Layer 3 of the OSI model and serve as boundaries between different networks. They prevent broadcast traffic from one network from spilling into another, thus controlling network congestion and improving security.

## IP Addressing

### IPv4 and IPv6

#### IPv4 Addressing
- **Format**: IPv4 uses a 32-bit address divided into four octets (e.g., 192.168.1.1).
- **Subnetting**: Subnet masks (e.g., 255.255.255.0) are used to divide the IP address into network and host portions.

#### IPv6 Addressing
- **Format**: IPv6 uses a 128-bit address written as eight groups of four hexadecimal digits (e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334).
- **Hexadecimal Representation**: Each "x" in the address represents a 16-bit block.
  
#### IPv6 Formatting Rules
- **Omit Leading Zeros**: Leading zeros within a block can be omitted (e.g., `0001` can be written as `1`).
- **Double Colon (::)**: Consecutive sections of zeros can be replaced with a double colon (e.g., `2001:0db8:0000:0000:0000:0000:1428:57ab` can be shortened to `2001:0db8::1428:57ab`).
  
### IPv4 and IPv6 Coexistence

#### Tunneling
- **Definition**: Tunneling allows IPv6 packets to be encapsulated within IPv4 packets to travel across an IPv4 network.
- **Types**: Common methods include 6to4, Teredo, and ISATAP.

#### Translation
- **Definition**: Network Address Translation (NAT) can be used to translate between IPv4 and IPv6 addresses.
- **Purpose**: This facilitates communication between IPv4-only and IPv6-only devices.

## DHCP Configuration

### Static and Dynamic Addressing
- **Static Addressing**: IP addresses are manually assigned to each device on the network, ensuring consistent addresses.
- **Dynamic Addressing**: DHCP servers automatically assign IP addresses to devices, simplifying management and reducing human error.

### DHCP Operation
- **DHCP Discover**: The client broadcasts a DHCP Discover message to find available DHCP servers.
- **DHCP Offer**: DHCP servers respond with an offer containing an available IP address.
- **DHCP Request**: The client requests the IP address from one of the offering servers.
- **DHCP Acknowledge**: The server acknowledges and assigns the IP address to the client, completing the process.

### DHCP Message Exchange
- **Discover**: The initial broadcast by the client to locate DHCP servers.
- **Offer**: The server’s response with an available IP address.
- **Request**: The client's formal request to use the offered address.
- **Acknowledge**: The server’s confirmation of the address assignment.

## Network Address Translation (NAT)

### Overview
- **Function**: NAT modifies the IP addresses in packet headers while they are in transit across a router, allowing multiple devices on a local network to share a single public IP address.
- **Types**:
  - **Static NAT**: One-to-one mapping between a local and public IP address.
  - **Dynamic NAT**: Maps an unregistered IP address to a registered IP address from a pool.
  - **PAT (Port Address Translation)**: Multiple local IP addresses are mapped to a single public IP address with different ports.

### NAT on Wireless Routers
- **Practical Example**: Using tools like Packet Tracer, you can examine how NAT is configured on a wireless router and how it translates IP addresses for internet access.

## TCP vs UDP

### Comparison
- **TCP (Transmission Control Protocol)**:
  - **Reliability**: Ensures reliable data transfer with error checking, acknowledgment, and retransmission.
  - **Connection-oriented**: Establishes a connection before data transfer begins.
  - **Use Cases**: Web browsing (HTTP/HTTPS), email (SMTP), file transfer (FTP).

- **UDP (User Datagram Protocol)**:
  - **Speed**: Faster than TCP as it lacks the overhead of error-checking and retransmission.
  - **Connectionless**: Sends packets without establishing a connection.
  - **Use Cases**: Streaming media, online gaming, VoIP.

### Port Numbers and Socket Pairs
- **Port Numbers**: Ports identify specific processes or services within a host. For example, HTTP typically uses port 80.
- **Socket Pairs**: A combination of an IP address and a port number, used to establish a connection between two devices.

### The NETSTAT Command
- **Usage**: `NETSTAT` is a network utility that displays active connections, routing tables, and network interface statistics. It's useful for diagnosing network issues and monitoring connections.

## Network Application Services

### Common Network Application Services
- **Web Clients and Servers**:
  - **HTTP/HTTPS**: HTTP is the protocol for transmitting web pages, while HTTPS provides secure transmission through encryption.
  - **FTP**: File Transfer Protocol allows for the transfer of files between a client and a server.
  
### Client and Server Interaction
- **Process**: Clients request services from servers, which then respond to these requests. For example, a web browser (client) sends a request to a web server, which responds with the requested web page.

### Network Boundaries
- **Definition**: Boundaries define the limits of network segments or domains, often established by routers.
- **Security**: Implementing boundaries helps contain broadcast domains and enforce security policies, controlling access between different parts of the network.


# Hierarchical Network Design (HND)

## 1. Hierarchical Network Design

### Overview
- **Definition**: Hierarchical Network Design is an approach to network design that organizes the network into layers or tiers, each serving a specific function. This structured approach improves the scalability, manageability, and performance of the network.
- **Layers in HND**:
  - **Core Layer**: The backbone of the network, responsible for fast and reliable data transport across the network. It connects all the major nodes and facilitates high-speed data transfer.
  - **Distribution Layer**: Serves as an intermediary between the Core and Access layers, providing routing, filtering, and network policy enforcement. It manages traffic, ensuring that data is efficiently routed to its destination.
  - **Access Layer**: The point where end devices like computers, printers, and IP phones connect to the network. It provides connectivity to the end users.

### Physical and Logical Address

- **Physical Address (MAC Address)**:
  - **Definition**: The Media Access Control (MAC) address is a unique identifier assigned to network interfaces for communications at the data link layer of a network segment.
  - **Format**: A MAC address is a 48-bit number typically represented as 12 hexadecimal digits (e.g., 00:1A:2B:3C:4D:5E).
  - **Use Case**: Used within a local network for communication between devices. It is crucial for the functioning of Ethernet and Wi-Fi networks.
  
- **Logical Address (IP Address)**:
  - **Definition**: An IP address is a logical identifier for a device on a network, assigned at the network layer (Layer 3) of the OSI model. It is used to route data between devices across networks.
  - **IPv4 Format**: A 32-bit number typically written in decimal format as four octets (e.g., 192.168.1.1).
  - **IPv6 Format**: A 128-bit number written in hexadecimal format (e.g., 2001:0db8:85a3::8a2e:0370:7334).
  - **Use Case**: IP addresses are used to identify devices on a network and route traffic to the correct destination.

## 2. Benefits of Hierarchical Network Design (HND)

### Scalability
- **Definition**: HND allows for easy expansion of the network by adding new layers or expanding existing ones without disrupting the overall network. This structured approach facilitates growth and adaptation to increasing network demands.

### Manageability
- **Definition**: With clearly defined layers, managing and troubleshooting the network becomes more straightforward. Each layer has specific functions, making it easier to isolate and address issues within the network.
- **Centralized Control**: The distribution layer allows centralized management of security policies, routing updates, and VLAN configurations.

### Performance
- **Improved Efficiency**: By segmenting the network into layers, data can be routed more efficiently, reducing latency and increasing the overall performance of the network.
- **Load Balancing**: Traffic is distributed evenly across the network, preventing bottlenecks and ensuring consistent performance.

### Redundancy and Fault Tolerance
- **Definition**: The hierarchical design supports redundancy, with multiple paths for data to travel, ensuring network availability even if one path fails. This fault tolerance minimizes downtime and maintains network reliability.

### Security
- **Enhanced Security**: Security policies can be enforced more effectively at the distribution layer, where traffic filtering, access control lists (ACLs), and firewall rules can be applied. This helps in securing the network against unauthorized access and threats.

### Viewing Network Information on Your Device

- **Using `ipconfig` (Windows)**:
  - **Purpose**: The `ipconfig` command displays all current TCP/IP network configuration values and refreshes DHCP and DNS settings.
  - **Basic Command**: 
    ```bash
    ipconfig
    ```
    - **Output**: Displays IP addresses, subnet masks, and default gateways for all network interfaces.
  
  - **Detailed View**:
    ```bash
    ipconfig /all
    ```
    - **Output**: Provides detailed information including MAC addresses, DNS servers, DHCP status, and lease information.

- **Other Useful Commands**:
  - **`ping`**: Tests connectivity to another network device or server.
    ```bash
    ping google.com
    ```
  - **`tracert` (Windows) / `traceroute` (Linux/Mac)**: Traces the path packets take to reach a destination.
    ```bash
    tracert google.com
    ```
  - **`netstat`**: Displays active connections, listening ports, and network statistics.
    ```bash
    netstat
    ```
  - **`nslookup`**: Queries DNS to obtain the domain name or IP address mapping.
    ```bash
    nslookup google.com
    ```
