## Flooding attacks
### ICMP Flooding

We can send ICMP(Internet Control Message Protocol) packets(Pings) to a specific host and typically it must respond, unless ICMP pings are de-activated.

---

### Source IP Spoofing / Reflection attacks

Spoofing the source ip address basically means we send packets with a modified source ip, which in this case is the ip of the victim.

We send packets on the victim's behalf to other hosts, which will respond and hopefully flood the interfaces.

We hope that for a small request we get a big response from the legit servers.

---

### TCP SYN Flooding

Each time a TCP connection is opened on a server, the latter must record info about the connection in a specific table.

By sending a lot of SYN packets we can overflow these tables and make the server unusable by making its resources anavailable. None of the connections will never conclude because we don't send any ACKs, so they are all retained in memory(hopefully).

---

### UDP Flood

Its cool because in UDP you don't have to establish a connection. 
In this attack we just send a lot of UDP packets to a specific port number on the target system.

---

### Slowloris - R.U.D.Y. (HTTP Flood)

Attempts to monopolize host resources by sending HTTP requests that never complete. This uses legitimate HTTP traffic. 
Take for example a GET request for a file, now imagine flooding that route.

Until you send 2 "\n", an HTTP GET is not considered over. Slowloris sends 1 byte every 10 seconds and consumes a lot of resources.

---

### DNS reflection attack

We use port 7 UDP echo?????????

---

### Amplification attack

Every single packet we send can generate multiple answers, so the attack gets amplified.

#### DNS Amplification attack

#### Memcached DDos Attack

15 byte request can generate 750kb, factor of 50000.

---
## Hardware?

### Botnet

Large collection of systems under the control of one attacker.

---

### Zombie

Attacker uses a flaw in the operating system to gain access and install malware on it, thus creating a zombie that can be used in botnet.

---

## Defenses

DDoS attacks can not be prevented entirely, because high traffic volumes may be legitimate.

### Blocks spoofed source addresses

No one does this but it could be done.

---

### ISP filters

The ISPs should verify that the packet is not spoofed, or filter it.

---

### Manage buffer overflows

Make sure to drop incomplete TCP connections when tables overflow.

---

### Protect sequence numbers

Use crypthography to protect sequence numbers in persistent connections.

---

### Anycast

Mitigating the attack by advertising multiple same ips across the world. 
A lot of packets will only reach one of these ip's and never reach the other ones, its basically load balancing at router/nodes level.
So depending on where the zombie is, it will only reach one of these hosts.

The attacker will send packets to intermediate router by using destination address, but the intermediate router is "told" by cloudflare(example) to send it to them.

Oh my god this is so fucking cool.