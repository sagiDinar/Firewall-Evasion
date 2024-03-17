# Firewall-Evasion
Firewall Evasion techniques with Nmap and Port tunneling.

# Decoy
nmap -sV -Pn -D 10.0.0.1, 10.10.0.12,RealIP Attacker, 172.16.1.13  "target ip"
#this technique wil obfuscate the real ip address of the attacker
nmap -sV -Pn -D RND,"REAL IP OF THE ATTACKER", RND, RND "target ip"

# Proxy
nmap -sV -Pn --proxies "IP OF THE PROXY OR URL" "target ip"
# Spoofed IP
nmap -sV -Pn -S "spoofed ip"

# Fixed src port
# If the attacker knows a port that allowd he can execute a port scat through this port
nmap -sV -Pn -g 80 "target ip"

# Data length and fragmentation
nmap -sS -Pn -f "target ip"

nmap -sS -Pn -ff "target ip"

nmap -sS -Pn --data-length 128 "target ip"

# Port tunneling useful wen you doing Lateral Movement
# In case you controled over server in the target network and you want to execute port scan on other ip address in the network, from your attacker machine, but the NGFw blocks you:

## In the controlled server run the command:
nc -lvnp 80 -c "the ip address you want to scan the port" 
## In the attacker machine:
nc "ip address of the controlled server" 80 
# The result will be the interaction with the ip address you want to scan the port



