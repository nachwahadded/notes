 bzip2 -d -f tmp/deploy/images/raspberrypi4/core-image-sato-raspberrypi4.wic.bz2

sudo dd if=tmp/deploy/images/raspberrypi4/core-image-sato-raspberrypi4.wic of=/dev/sdb bs=1MB