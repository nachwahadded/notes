
if dhcp doesn't work when [[add  Wifi drivers]] 


dhcp 
`auto wlan0 
`iface wlan inet dhcp 
`wireless_mode managed 
`wpa-conf /etc/wpa_supplicant.conf


static

auto wlan0
iface wlan0 inet static
    address 192.168.1.10
    netmask 255.255.255.0
    gateway 192.168.1.1