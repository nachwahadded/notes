
after  setting [[add  Wifi drivers]]   and correcting [[static and dhcp]]  you may encounter a problem in pi,ging to google 


first Check IPv6 Connectivity:
Before troubleshooting IPv4, ensure that your Yocto device has proper IPv6 connectivity. You can try pinging an IPv6 address, such as Google's IPv6 DNS server.

`ping6 2001:4860:4860::8888

then  set a ipv4  address 
`ifconfig wlan0 192.168.1.1 

then  add a default route using the ip route command is:

`sudo ip route add default via 192.168.1.1 dev wlan0


/etc/resolv.conf

`nameserver 8.8.8.8
`nameserver 8.8.4.4

After updating the DNS configuration, restart networking services to apply the changes:
``/etc/init.d/networking restart


ping 8.8.8.8
ping google.com
