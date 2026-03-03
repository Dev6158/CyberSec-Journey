# Networking Notes

## 1. OSI Model (Explained Simply)

The OSI model is a 7-layer framework that explains how data moves from one device to another over a network. Each layer has a specific responsibility.

### 1. Physical Layer (Layer 1)
This layer deals with the actual hardware. It sends raw bits (0s and 1s) through cables, fiber, or wireless signals. It defines voltage levels, cables, connectors, and transmission speed.

### 2. Data Link Layer (Layer 2)
This layer ensures data moves correctly between two directly connected devices. It organizes bits into frames and uses MAC addresses. It can also detect errors in transmission.

### 3. Network Layer (Layer 3)
Responsible for logical addressing and routing. It uses IP addresses to decide how packets travel from source to destination across multiple networks.

### 4. Transport Layer (Layer 4)
Ensures reliable or fast delivery of data between systems. It breaks data into segments and manages flow control and error handling. TCP and UDP operate here.

### 5. Session Layer (Layer 5)
Manages sessions between applications. It establishes, maintains, and terminates communication sessions.

### 6. Presentation Layer (Layer 6)
Handles data formatting. It ensures data is in a readable format for the application. It manages encryption, compression, and translation.

### 7. Application Layer (Layer 7)
The closest layer to the user. It provides network services directly to applications like browsers, email clients, and file transfer tools.

---

## 2. TCP vs UDP

Both TCP and UDP operate at the Transport Layer but behave differently.

### TCP (Transmission Control Protocol)
- Connection-oriented (requires handshake before sending data)
- Reliable (guarantees delivery)
- Ordered (data arrives in sequence)
- Slower due to error checking and acknowledgments

Used in:
- Web browsing (HTTP/HTTPS)
- Email
- File transfers
- Banking systems

### UDP (User Datagram Protocol)
- Connectionless (no handshake)
- Faster but unreliable
- No guarantee of delivery or order
- Low overhead

Used in:
- Video streaming
- Online gaming
- VoIP calls
- DNS queries

Summary:  
Use TCP when reliability matters. Use UDP when speed matters more than perfect accuracy.

---

## 3. 10 Common Protocols and Port Numbers

| Protocol | Port Number | Purpose |
|----------|------------|----------|
| HTTP     | 80         | Web traffic (unencrypted) |
| HTTPS    | 443        | Secure web traffic |
| FTP      | 21         | File transfer |
| SSH      | 22         | Secure remote login |
| Telnet   | 23         | Remote login (insecure) |
| SMTP     | 25         | Sending email |
| DNS      | 53         | Domain name resolution |
| DHCP     | 67/68      | Automatic IP assignment |
| POP3     | 110        | Receiving email |
| IMAP     | 143        | Email synchronization |

---

## 4. How DNS Works (Step by Step)

DNS converts domain names into IP addresses.

Example: You type `kiit.ac.in` in your browser.

**Step 1: Browser Cache Check**  
The browser checks if it already knows the IP address.

**Step 2: OS Cache Check**  
If not found, the operating system checks its local DNS cache.

**Step 3: Recursive Resolver**  
If still not found, the request is sent to a DNS resolver (usually provided by ISP).

**Step 4: Root Server Query**  
The resolver asks a root DNS server where to find information about the top-level domain (.com).

**Step 5: TLD Server Query**  
The resolver then asks the TLD server which authoritative server knows the domain.

**Step 6: Authoritative Server**  
The authoritative DNS server provides the correct IP address.

**Step 7: Response Returned**  
The resolver sends the IP back to your system and caches it.

**Step 8: Connection Established**  
Your browser now connects to the web server using that IP address.
