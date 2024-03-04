>Increase Inotify Limits:  The Linux kernel has limits on the number of inotify watches that can be created. You can check the current limits using:


`cat /proc/sys/fs/inotify/max_user_watches

If the limit is low, you can increase it temporarily using: and set the desired value 

`sudo sysctl -w fs.inotify.max_user_watches=524288

To make the change permanent, add the following line to /etc/sysctl.conf:


`fs.inotify.max_user_watches=524288 
Then run `
`sudo sysctl -p to apply the changes.


