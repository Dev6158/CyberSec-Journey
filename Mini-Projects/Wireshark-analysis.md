# Wireshark Network Analysis

This mini project documents network traffic captured using Wireshark for several minutes.  
The objective was to observe real network packets and identify different protocols used during normal internet activity.

The capture was performed on the `eth0` interface while browsing websites and generating traffic.  
The following protocols were analyzed:

- DNS
- TCP
- HTTP / OCSP
- TLS
- ICMP

---

# Packet 1: DNS Packet

<img width="1920" height="1083" alt="dns" src="https://github.com/user-attachments/assets/f50bee17-edce-4932-938e-3342f37f2a1d" />


**Protocol:** DNS (Domain Name System)

**Source:** 10.0.2.15  
**Destination:** 10.0.2.3

**What is happening:**

This packet is a DNS query and response. The system sends a request to the DNS server to resolve domain names such as `youtube.com` or `gstatic.com` into their corresponding IP addresses.

DNS acts like the internet’s phonebook. Instead of remembering numerical IP addresses, users type domain names and DNS servers translate them into the correct IP address.

In the capture we can see responses returning multiple IP addresses for Google and YouTube services.

---

# Packet 2: TCP Packet

<img width="1920" height="1083" alt="tcp" src="https://github.com/user-attachments/assets/c795ad26-53d9-460b-834e-6d226f0200b8" />


**Protocol:** TCP (Transmission Control Protocol)

**Source:** 10.0.2.15  
**Destination:** External web servers (example: 142.250.70.78)

**What is happening:**

This packet belongs to a TCP connection between the local machine and a remote server. TCP ensures reliable data transfer by maintaining a connection between two devices.

The packet information shows acknowledgement flags (`ACK`) and sequence numbers, which are part of TCP's mechanism to ensure that data is delivered in order and without loss.

TCP is used by most internet services such as web browsing, file transfers, and email.

---

# Packet 3: HTTP / OCSP Packet

<img width="1920" height="1083" alt="http" src="https://github.com/user-attachments/assets/b157d8a3-8ba8-4d8c-9bd0-b2d57e7fb8be" />


**Protocol:** HTTP / OCSP (Online Certificate Status Protocol)

**Source:** 10.0.2.15  
**Destination:** 142.250.77.35

**What is happening:**

This packet shows HTTP communication related to OCSP requests. OCSP is used by browsers to verify whether a website’s SSL/TLS certificate is still valid or has been revoked.

When visiting secure websites, the browser checks with a certificate authority to confirm the authenticity of the server's certificate.

The capture shows OCSP requests and responses used during this certificate validation process.

---

# Packet 4: TLS Packet

<img width="1920" height="1083" alt="tls" src="https://github.com/user-attachments/assets/78fd0bc8-4fd3-47e2-9dd4-ef4f724df59e" />


**Protocol:** TLSv1.3 (Transport Layer Security)

**Source:** 10.0.2.15  
**Destination:** Various remote servers

**What is happening:**

TLS packets represent encrypted communication between the client and web servers. After the TCP connection is established and the TLS handshake is completed, data transmitted between the browser and the server becomes encrypted.

The captured packets are labeled **Application Data**, meaning the content is encrypted and cannot be read directly by Wireshark.

TLS is used by HTTPS websites to protect sensitive information such as login credentials and personal data.

---

# Packet 5: ICMP Packet

<img width="1920" height="1083" alt="icmp" src="https://github.com/user-attachments/assets/02b2334d-833b-4ac1-b013-b8ec68bb02f7" />


**Protocol:** ICMP (Internet Control Message Protocol)

**Source:** 10.0.2.2  
**Destination:** 10.0.2.15

**What is happening:**

This packet shows an ICMP error message indicating **Destination Unreachable (Port Unreachable)**. ICMP is commonly used for network diagnostics and error reporting.

These messages occur when a device attempts to send data to a port or service that is not available on the destination system.

ICMP is also used by tools such as `ping` to test network connectivity.

---

# Methodology

1. Opened Wireshark and selected the `eth0` interface.
2. Started packet capture for approximately 5 minutes.
3. Generated traffic by:
   - Visiting websites such as Google and YouTube.
   - Running basic network requests.
4. Applied display filters to isolate specific protocols:
   - `dns`
   - `tcp`
   - `http`
   - `tls`
   - `icmp`
5. Selected representative packets for analysis and captured screenshots.

---

# Observations

- The majority of packets captured were **TCP and TLS**, showing that most modern internet traffic is encrypted.
- DNS queries appeared whenever a domain name needed to be resolved into an IP address.
- OCSP packets appeared during HTTPS connections to verify certificate validity.
- ICMP packets showed diagnostic responses such as **destination unreachable** messages.
- The address `10.0.2.15` indicates the capture was performed inside a **virtual machine NAT network environment**.

---

# Conclusion

This analysis demonstrates how multiple network protocols interact during normal internet usage.

DNS resolves domain names into IP addresses, TCP establishes reliable communication between devices, TLS encrypts the data being transmitted, HTTP handles web communication, and ICMP provides network diagnostic messages.

Using Wireshark makes it possible to observe these protocols in real time and better understand how data moves across computer networks.
