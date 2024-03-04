`adb root
`adb shell setenforce 0 &&  adb shell umount -l -t overlay /system_ext 2> /dev/null   && adb remount

`then  enter with 
`adb shell 
`mount -o remount;rw /system