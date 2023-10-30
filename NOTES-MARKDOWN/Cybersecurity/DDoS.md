## Flooding attacks
### ICMP Flooding

We can send ICMP(Internet Control Message Protocol) packets(Pings) to a specific host and typically it must respond, unless ICMP pings are de-activated.

---

### Source IP Spoofing

Spoofing the source ip address basically means we send packets with a modified source ip, which in this case is the ip of the victim.

We send packets on the victim's behalf to other hosts, which will respond and hopefully flood the interfaces.

---

### TCP SYN Flooding

Each time a TCP connection is opened on a server, the latter must record info about the connection in a specific table.

By sending a lot of SYN packets we can overflow these tables and make the server unusable by making its resources anavailable. None of the connections will never conclude because we don't send any ACKs, so they are all retained in memory(hopefully).

---

### UDP Flood

Its cool because in UDP you don't have to establish a connection. 
In this attack we just send a lot of UDP packets to a specific port number on the target system.

---

## Hardware?