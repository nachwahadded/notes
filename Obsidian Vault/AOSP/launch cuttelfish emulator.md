`lunch 20
 `mm -j8
 
`cd device/google/cuttlefish

`grep -R TARGET_BOARD_PLATFORM *
`ls -ll out/target/product/vsoc_x86/*.img

Building using CD/CI :
    In a terminal window, download, build, and install the host Debian packages:

 
`sudo apt install -y git devscripts config-package-dev debhelper-compat golang curl
`git clone https://github.com/google/android-cuttlefish 

choose the version stable 28 
`git checkout xxxxxx`

`cd android-cuttlefish
`cd base /debian 
 `debuild -i -us -uc -b -d
 `debuild --check-dirname-level 0
 `sudo dpkg -i ./cuttlefish-base_*_*64.deb || sudo apt-get install -f
`sudo dpkg -i ./cuttlefish-user_*_*64.deb || sudo apt-get install -f
`sudo usermod -aG kvm,cvdnetwork,render $USER
`sudo reboot

On your local system, create a container folder and extract the packages:


`mkdir cf
`cd cf
`tar -xvf /path/to/cvd-host_package.tar.gz
`unzip /path/to/aosp_cf_x86_64_phone-img-xxxxxx￼.zip

Launch Cuttlefish:
 
`HOME=$PWD ./bin/launch_cvd --daemon



!lthe i can access with adb shell 
  