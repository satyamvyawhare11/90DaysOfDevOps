# Day 15 – Networking Concepts: DNS, IP, Subnets & Ports

Today I focused on understanding the core networking concepts that every DevOps engineer must know.
Instead of just memorizing terms, I tried to understand how things actually work together in real systems.

---

## Task 1: DNS – How Names Become IPs

### What happens when you type google.com in a browser?

When I type google.com:
1. The browser asks the system to resolve the domain name.
2. The system queries a DNS resolver.
3. DNS returns the IP address for the domain.
4. The browser connects to that IP using TCP.
5. The web server responds using HTTP/HTTPS.

DNS works like a phonebook that converts names into IP addresses.

---

### DNS Record Types

- **A** – Maps a domain name to an IPv4 address  
- **AAAA** – Maps a domain name to an IPv6 address  
- **CNAME** – Alias that points one domain to another domain  
- **MX** – Specifies mail servers for a domain  
- **NS** – Specifies authoritative name servers for a domain  

---

### DNS Command Observation

Command used:
- `dig google.com`

What I observed:
- The ANSWER section showed IPv4 addresses (A records).
- TTL value tells how long the DNS response is cached.

---

## Task 2: IP Addressing

### What is an IPv4 address?

An IPv4 address is a 32-bit number written in four parts.
Each part ranges from 0 to 255.

Example:
- 192.168.1.10

---

### Public vs Private IP

- **Public IP**
  - Reachable from the internet
  - Example: 8.8.8.8

- **Private IP**
  - Used inside private networks (cloud, office, home)
  - Example: 172.31.12.41

---

### Private IP Ranges

- 10.0.0.0 – 10.255.255.255  
- 172.16.0.0 – 172.31.255.255  
- 192.168.0.0 – 192.168.255.255  

---

### My IP Address

Command used:
- `ip addr show`

Observation:
- My server IP `172.31.12.41` is a private IP.
- It is assigned to the main network interface.

---

## Task 3: CIDR & Subnetting

### What does /24 mean?

`/24` means the first 24 bits are used for the network.
The remaining bits are used for hosts.

Example:
- 192.168.1.0/24

---

### Why do we subnet?

Subnetting is used to:
- Organize networks better
- Improve security
- Reduce broadcast traffic
- Separate applications and databases

---

### CIDR Table

| CIDR | Subnet Mask        | Total IPs | Usable Hosts |
|-----|--------------------|-----------|--------------|
| /24 | 255.255.255.0      | 256       | 254          |
| /16 | 255.255.0.0        | 65,536    | 65,534       |
| /28 | 255.255.255.240    | 16        | 14           |

Note:
- Network IP and Broadcast IP are not usable.

---

## Task 4: Ports – The Doors to Services

### What is a port?

A port identifies which service should receive the traffic.
One IP can run multiple services using different ports.

---

### Common Ports

| Port | Service   |
|-----|-----------|
| 22  | SSH       |
| 80  | HTTP      |
| 443 | HTTPS     |
| 53  | DNS       |
| 3306 | MySQL   |
| 6379 | Redis   |
| 27017 | MongoDB |

---

### Listening Ports on My System

Command used:
- `ss -tulpn`

Observation:
- SSH is listening on port 22
- Nginx is listening on port 80
- One application is listening on port 8080

---

## Task 5: Putting It Together

### curl http://myapp.com:8080 – What happens?

- DNS resolves myapp.com to an IP
- TCP connection is made to port 8080
- HTTP request is sent to the application
- Application sends a response

---

### App can’t reach DB at 10.0.1.50:3306 – What to check first?

1. Check if the IP is reachable
2. Check if port 3306 is open
3. Check firewall or security group rules
4. Check if database service is running

---

## What I Learned

- DNS, IPs, ports, and subnets work together, not separately
- Most networking issues can be solved by checking the correct layer
- Understanding basics makes troubleshooting much easier
