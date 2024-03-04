route add -host 224.0.0.1 dev eth0 &
#matchbox-desktop &


ifconfig eth0 10.0.0.5 &

cd /home/root
sh client.sh 