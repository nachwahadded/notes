to add a specific recipe  to the raspberry image being built [[build image raspberry  yocto]]


### cteate a recipe under  source/meta-raspberry 


`mkdir recipes-vsomeip
`mkdir vsomeip
`gedit vsomeip-version .bb (ex :vsomeip_3.1.37.1.bb )

### the .bb 
>SUMMARY = "Implementation of SOME/IP"
SECTION = "base"
LICENSE = "MPLv2"
LIC_FILES_CHKSUM = "file://LICENSE;md5=815ca599c9df247a0c7f619bab123dad"
DEPENDS = "boost"
SRCREV = "11447b294a5ad4d8be08a466f769670aa7ed924a" 
SRC_URI = "git://github.com/GENIVI/vsomeip.git;protocol=https"
S = "${WORKDIR}/git"
inherit cmake 
PACKAGES_remove += "${PN}-bin"
FILES_${PN}-dev += "${libdir}/cmake"
FILES_${PN}-dev += "${includedir}/*"
FILES_${PN} += "${libdir}/libvsomeip*"
FILES_SOLIBSDEV = ""
INSANE_SKIP_${PN} += "dev-so"
do_install_append() {
    mv  ${D}/usr/etc ${D}
}





### bitbake 
first do bitbake for the  desired recipe
`
`bitbake vsomeip
then  

`bitbake core image-sato
like mentioned in [[build image raspberry  yocto]]as well 
