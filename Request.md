# What Happens When search google.com in your browser and press enter

When you type https://www.google.com into your browser and hit Enter, a fascinating journey begins - transcending various layers of the web stack before the desired webpage graces your screen.

## The initiation: DNS Request
The browser seeks to transform the human-readable domain name (www.google.com) into an IP address. This is done through a DNS (Domain Name System) request. The browser checks its local cache first, then queries the configured DNS server, which may involve multiple steps through various DNS servers until it retrieves the IP address associated with www.google.com.

## TCP/IP
TCP (Transmission Control Protocol) and IP (Internet Protocol) are two of the primary protocols that constitute the internet. They work in conjunction to establish a link between a client and a server and facilitate the exchange of data between them. When you input "google.com" into a web browser, the browser employs TCP/IP to establish a link with the server that hosts the website.

- The browser uses IP to send a request to the server to establish a connection.
- The server receives the request and sends a message back acknowledging the request to establish a connection. This is known as the handshake procedure.
- Once the handshake is completed, the browser can use TCP to send a request for the webpage it wants to access (in this instance, the homepage of google.com). This request is made using TCP, which ensures that the request is sent reliably and in the correct sequence.
- The server receives the request and sends the HTML code for the homepage of google.com back to the browser. This response is also sent using TCP to ensure dependable transmission.
- The browser receives the HTML code and uses it to display the webpage on your screen. Any resources (such as images) that the webpage requires are also requested and received using TCP/IP.


## Firewall and Security Checks
Before the request reaches the server, it may pass through various firewalls and security checks. These systems inspect the request for malicious content, ensuring that it adheres to security policies and does not pose a threat to the network.

There are two primary types of security policies that a firewall employs to examine incoming requests:



1. **Policies that allow or prohibit traffic based on the origin and destination of the request.** For example, a firewall may be programmed to block all traffic from specific countries or to allow only specific IP addresses to access the network.
2. **Policies that allow or prohibit traffic based on the type of traffic.** For example, a firewall may be programmed to block all traffic on certain ports (such as those used by malware) or to allow only certain types of traffic (such as HTTP or HTTPS).

## Secure package: HTTP/HTTPS
Once the TCP connection is established, the browser sends an HTTP (Hypertext Transfer Protocol) or HTTPS (HTTP Secure) request to the server. If HTTPS is used, the browser and server perform an SSL/TLS handshake to establish a secure connection, which involves:
1. **Certificate Verification**: The server presents its SSL/TLS certificate to the browser, which verifies its authenticity against trusted Certificate Authorities (CAs).
2. **Session Key Generation**: The browser and server generate a session key for encrypting the data exchanged during the session.
3. **Secure Connection Established**: Once the handshake is complete, the browser can securely communicate with the server.

## Load Balancing
At googles premises a load balancer takes the packets. its role is to distribute incoming requests across multiple servers to ensure optimal performance and reliability. The load balancer uses various algorithms (like round-robin, least connections, etc.) to determine which server should handle the request to ensure no single server becomes overwhelmed with too much traffic.

## Web server
Post load balancing the web server takes the stage, handling the HTTP request. It decides which action is needed based on the request type (GET, POST, etc.) and the requested resource (like a webpage, image, etc.).

## Application Server
It is the brain behind the operation, executing the necessary business logic to generate the requested content. This may involve querying databases, processing data, and preparing the final response to be sent back to the browser.

## Database Query
To fulfill your request, the application server may need to query a database. This involves:
1. **SQL Query**: The application server constructs an SQL (Structured Query Language) query to retrieve the necessary data.
2. **Database Connection**: The application server establishes a connection to the database server, which may involve additional security checks and authentication.
3. **Data Retrieval**: The database server processes the query and returns the requested data to the application server.
4. **Data Formatting**: The application server formats the data into a suitable response format (like HTML, JSON, etc.) to be sent back to the browser.

## Response
The HTTP response makes its way back through the channels, reaching your browser which then renders the HTML, CSS, and JavaScript to display the webpage we all know and love as Google.


