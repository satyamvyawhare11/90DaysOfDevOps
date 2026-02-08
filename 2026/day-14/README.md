# Day 14 – Networking Fundamentals & Hands-on Checks

Today I practiced core Linux networking commands and focused on understanding
how to diagnose connectivity issues layer by layer, like a DevOps engineer.

The goal was not just to run commands, but to interpret what they mean in real systems.

---

## Quick Concepts

### OSI vs TCP/IP (My Understanding)
- OSI is a learning model with 7 layers.
- TCP/IP is the practical implementation used in real systems.
- Networking issues are solved by identifying the broken layer first.

### Protocol Placement
- IP → Network layer (addressing & routing)
- TCP/UDP → Transport layer (delivery)
- DNS, HTTP/HTTPS, SSH → Application layer

Example:
Accessing a website uses HTTP (Application) over TCP (Transport) over IP (Network).

---

## Hands-on Observations

### Identity Check
Command used:
- `hostname -I`
- `ip addr show`

Observation:
- My EC2 instance has a private IP `172.31.12.41`.
- Docker bridge network `172.17.0.1` is also present.
- Confirms the server is connected to the VPC network.

---

### Reachability Check
Command used:
- `ping trainwithshubham.com`
- `ping google.com`

Observation:
- Both targets responded with **0% packet loss**.
- Latency was very low (< 1 ms).
- Confirms network connectivity is healthy.

Note:
- Ping failed when domain name was incorrect (DNS-related learning).

---

### Path Analysis
Command used:
- `traceroute trainwithshubham.com`
- `tracepath google.com`

Observation:
- Initial hops responded.
- Many later hops showed `* * *`.
- This is common in cloud environments where ICMP is blocked.

Learning:
- Missing traceroute replies do not always indicate a network failure.

---

### Ports & Services Check
Command used:
- `ss -tulpn`
- `netstat -tulpn`

Observation:
- SSH is listening on port 22.
- Nginx is listening on port 80.
- A local service is listening on port 8080.

Learning:
- If a service is not listening on a port, it cannot receive traffic.

---

### DNS Resolution
Command used:
- `nslookup trainwithshubham.com`

Observation:
- Domain resolved to multiple IP addresses.
- Confirms DNS is working correctly.

Learning:
- DNS issues can break everything even if the network is up.

---

### HTTP Check
Command used:
- `curl -I trainwithshubham.com`
- `curl -I google.com`

Observation:
- trainwithshubham.com returned `405 Not Allowed`
- google.com returned `301 Moved Permanently`

Learning:
- HTTP errors do not always mean network issues.
- Application logic and security rules also affect responses.

---

### Connections Snapshot
Command used:
- `netstat -an | head`

Observation:
- SSH connection shown as `ESTABLISHED`.
- Multiple services in `LISTEN` state.

Learning:
- Useful for identifying active and stuck connections.

---

## Mini Task – Port Probe

Command used:
- `nc -zv localhost 80`
- `nc -zv localhost 22`

Observation:
- Both ports were reachable locally.
- Confirms services are running and accepting connections.

Next steps if failed:
- Check service status
- Check firewall rules
- Verify correct port binding

---

## Key Learnings

- Networking troubleshooting must follow layers, not guesswork.
- Ping checks reachability, not application health.
- DNS failures can block access even when servers are reachable.
- Ports must be listening for services to be accessible.
- Disk issues can indirectly cause networking and package failures.

---

## Reflection

- Fastest signal command: `ping`
- If DNS fails → investigate Application/DNS layer first
- If HTTP returns 500 → network is fine, application is the issue
- Next checks in real incident:
  - Service status
  - Logs
  - Disk usage

Happy Learning  
**TrainWithShubham**
