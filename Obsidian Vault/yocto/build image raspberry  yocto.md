### The first step is to install the prerequisite for Yocto. 
`sudo apt-get install gawk wget git-core diffstat unzip texinfo gcc-multilib \
     `build-essential chrpath socat cpio python3 python3-pip python3-pexpect \
     `xz-utils debianutils iputils-ping python3-git python3-jinja2 libegl1-mesa libsdl1.2-dev \
     `pylint3 xterm
### Getting the meta layers

>Before getting any meta layers we’re gonna create a project folder named `yocto` and a folder named `source` for all the meta layers inside.

`mkdir yocto  
`cd yocto  
`mkdir sources

>The meta layer we’re always needing is poky. It contains all the basic stuff for yocto to work. We get it by executing the following git command.

`git clone git://git.yoctoproject.org/poky -b dunfell

F>or the Raspberry Pi, there is a nicely made meta layer with all the definitions needed to run the Raspberry Pi. We get it with this command.

`git clone git://git.yoctoproject.org/meta-raspberrypi -b dunfell

Meta layers always state on which meta layers they depend. The readme of [meta-raspberrypi](http://git.yoctoproject.org/cgit/cgit.cgi/meta-raspberrypi/tree/README.md?h=dunfell) states that we need poky, which we already have, and `meta-openembedded`. This meta-layer itself is divided into multiple layers. We get them all by this command.

`git clone [https://git.openembedded.org/meta-openembedded](https://git.openembedded.org/meta-openembedded) -b dunfell

>Those are all the meta layers we need. Let’s go back to our project folder and initialize the build environment.

`cd ..   
``. sources/poky/oe-init-build-env


The `bblayers.conf` file in the `conf` folder contains all the path to the meta layers we're gonna use.

`nano conf/bblayers.conf

`local.conf` file in the `conf` folder does contain some basic configurations and, most important for us, the name of the machine to build for. If we want to build for the Raspberry Pi 4, we're using `raspberrypi4`

`nano conf/local.conf[...]MACHINE ?= "raspberrypi4"[...]

### build the desired image 

`bitbake core-image-sato 

### Decopmress the image 

`bzip2 -d -f tmp/deploy/images/raspberrypi4/core-image-base-raspberrypi4.wic.bz2

You only have to flash it to an SD-Card like any other Raspian image, and you’re ready to boot.

### flash the image  
 ` bzip2 -d -f tmp/deploy/images/raspberrypi4/core-image-sato-raspberrypi4.wic.bz2