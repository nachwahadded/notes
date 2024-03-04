1/create desktop shortcut for an AppImage:


-sudo mv filename.AppImage /opt/
-sudo mv your-icon-name.png /opt/
-sudo nano /usr/share/applications/NextCloud.desktop

-Desktop Entry]
Name=Nextcloud
Exec=/opt/nextcloud.AppImage
Icon=/opt/nextcloud-icon.png
comment=cloud
Type=Application
Terminal=false
Encoding=UTF-8
Categories=Utility;

-sudo cp -r /usr/share/applications/NextCloud.desktop ~/Desktop/
==>do chmox and it will be available 




------omxplayer in the onfig.txt---------------
 driver audio 
PACKAGECONFIG_append_pn-mesa = " vc4"  
IMAGE_INSTALL_append = " xf86-video-modesetting xf86-video-fbdev"  
DISTRO_FEATURES_append = " opengl"  
KERNEL_MODULE_AUTOLOAD += "vc4"

deiver video 
IMAGE_INSTALL_append = " alsa-utils alsa-state"  
IMAGE_INSTALL_append = " pulseaudio"  
KERNEL_MODULE_AUTOLOAD += "snd-bcm2835 bcm2835-v4l2"


yocto/sources/meta-raspberrypi/recipes-kernel/linux/files  

vc4graphics.cfg

CONFIG_I2C_BCM2835=y  
CONFIG_DRM=y  
CONFIG_DRM_FBDEV_EMULATION=y  
CONFIG_DRM_VC4=y  
CONFIG_DRM_V3D=y  
CONFIG_SND=y