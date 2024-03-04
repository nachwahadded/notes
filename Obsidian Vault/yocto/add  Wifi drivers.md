   ****** ----in local.conf -----*****
 
IMAGE_INSTALL_append = " wpa-supplicant"


Create a file named wpa_supplicant.conf with the following content:

/**with security**/ 
ctrl_interface=/var/run/wpa_supplicant
ctrl_interface_group=0
update_config=1

network={
        key_mgmt=NONE
}

network={
        ssid="noch"
        psk="12345678"
        key_mgmt=WPA-PSK
        proto=RSN
        pairwise=CCMP
}

/etc/init.d/wpa_supplicant restart
wpa_supplicant -B -i wlan0 -c /etc/wpa_supplicant.conf
wpa_supplicant  -i wlan0 -c /etc/wpa_supplicant.conf : to show the logs 


rfkill unblock wlan

