# Week 1: Networking Challenge Solution 

# Tasks
# Understand OSI & TCP/IP Models

# Application Layer (Layer 7)
Protocol Examples: HTTP, FTP, SMTP

The Application Layer is responsible for enabling communication between software applications. It's the layer closest to the end-user, where protocols used for web browsing, email, and file transfer reside.

Example:

HTTP (HyperText Transfer Protocol): When you type a URL in your web browser (e.g., https://www.hashnode.com), the browser sends an HTTP request to a web server to load the requested page. The server responds with the requested data (HTML, CSS, JS) in an HTTP response.

# Presentation Layer (Layer 6)
Protocol Examples: SSL/TLS, JPEG, ASCII

The Presentation Layer is responsible for translating, encrypting, or compressing data. It's like the translator between the application data format and the transmission format.

Example:

SSL/TLS (Secure Sockets Layer / Transport Layer Security): When you visit a website over HTTPS (e.g., https://www.hashnode.com), the data being exchanged is encrypted using SSL/TLS to ensure security. SSL/TLS ensures that the communication between the browser and the web server is private and secure.

# Session Layer (Layer 5)
Protocol Examples: NetBIOS, RPC (Remote Procedure Call)

The Session Layer manages and controls the dialog between two computers, handling the opening, closing, and management of sessions. It’s where the connection between two devices is established, maintained, and terminated.

Example:

Remote Procedure Call (RPC): When a user interacts with a remote service, like a cloud-based application (e.g., a document editing tool), the Session Layer ensures that multiple requests between the client and server are kept in sync. This ensures that the client can send requests, wait for responses, and manage the state between multiple sessions.


# Transport Layer (Layer 4)
Protocol Examples: TCP, UDP

The Transport Layer is responsible for ensuring that data is transferred reliably and in the correct order. It handles end-to-end communication, error correction, and data flow control.

Example:

TCP (Transmission Control Protocol): When you access a webpage (e.g., www.hashnode.com), TCP ensures that all the data packets sent from the web server to your browser are received correctly and in the right order. If any packet is lost, TCP will resend it to ensure complete and accurate data delivery.


# Network Layer (Layer 3)
Protocol Examples: IP, ICMP

The Network Layer is responsible for determining how data is routed from source to destination across multiple networks. It handles logical addressing and routing.

Example:

IP (Internet Protocol): When you access a website, your request goes through the IP network. The IP protocol ensures that your request is sent to the correct destination (e.g., the Hashnode server) by using IP addresses. Routers at different points along the network path ensure the request reaches its destination.


# Data Link Layer (Layer 2)
Protocol Examples: Ethernet, Wi-Fi (802.11), PPP

The Data Link Layer is responsible for the physical transmission of data over a medium. It deals with the frames that encapsulate packets for transmission over a physical link, like cables or wireless connections.

Example:

Ethernet: When your computer is connected to a local area network (LAN), Ethernet handles the packaging of data into frames for transmission. Whether you're using wired Ethernet or Wi-Fi, this layer ensures the data is formatted for the physical transmission medium.


# Physical Layer (Layer 1)
Protocol Examples: Cables, Radio Waves, Fiber Optic

The Physical Layer deals with the actual hardware transmission of raw data over the physical medium, such as electrical impulses, light signals, or radio waves. It defines the hardware and transmission methods.

# Example:

Ethernet Cable: When you're connected to the internet via a wired connection, Ethernet cables (with copper wires) or fiber optics transmit electrical signals or light to send data between devices. The physical layer is responsible for the transmission of raw binary data (0s and 1s) through these mediums.
In a Real-World Example (Web Browsing):

Application Layer: Your browser (e.g., Chrome) makes an HTTP request to fetch a web page from Hashnode.

Presentation Layer: The browser encrypts your request using SSL/TLS to ensure security.

Session Layer: A session is established between your browser and the Hashnode server.

Transport Layer: TCP ensures that all packets of the web page data are delivered reliably to your browser.

Network Layer: The request is routed to the Hashnode server via the Internet using IP addresses.

Data Link Layer: The data is transmitted through your local network using Ethernet or Wi-Fi.

Physical Layer: Finally, the raw bits are transmitted over the physical medium—whether it's fiber optics, copper wires, or radio waves for Wi-Fi.
