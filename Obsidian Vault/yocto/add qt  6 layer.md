

to add a specific layer to the raspberry image being built [[build image raspberry  yocto]]
### ## Yocto version support
 
Yocto \ Qt	6.2	6.1	6.0
master	x		
honister	x		
hardknott	x	x	x
gatesgarth	c	x	x
dunfell	x	x	x


### unde poky clone the repository


`git clone https://github.com/victronenergy/meta-qt6.git

### add meta-qt6  to bblayers.conf 

 `` /home/nahaddad/Documents/yocto/sources/poky/meta-qt6\


### bitbake 

bitake core image-sato like mentioned in [[build image raspberry  yocto]]as well 

 