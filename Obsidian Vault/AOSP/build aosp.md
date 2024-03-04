#### INITIALIZING A REPO CLIENT 


`mkdir aosp12
`cd aosp12

#### CONFIGURE GIT WITH YOUR REAL NAME AND EMAIL ADDRESS


`git config --global user.name nachwa
`git config --global user.email nachwa.haddad@actia-engineering.tn

#### INSTALL ANDROID REPO ON UBUNTU SYSTEM 

`mkdir -p ~/.bin
`PATH="${HOME}/.bin:${PATH}"
`curl https://storage.googleapis.com/git-repo-downloads/repo > ~/.bin/repo
`chmod a+rx ~/.bin/repo


#### DOWNLOAD ANDROID SOURCE WITH LOCAL_MANIFESTS
`repo init -u https://android.googlesource.com/platform/manifest -b android-12.1.0_r21
`git clone https://github.com/android-rpi/local_manifests .repo/local_manifests -b arpi-12
`repo sync -j8

#### BUILD ANDROID

`sudo apt install libssl-dev python3-setuptools 
`source build/envsetup.sh
`lunch rpi4-eng
`make ramdisk systemimage vendorimage
 
#### PREPARE SD CARD
 `cd out/target/product/rpi4
  `sudo dd if=system.img of=/dev/<p2> bs=1M
  `sudo dd if=vendor.img of=/dev/<p3> bs=1M
  
#### TEST ON RASPBERRY 
  `adb devices 
    `adb push 
`adb push code_name  /data
`cd date
``./code_name


https://www.codeinsideout.com/blog/android/build-aosp/#build-**tricks**