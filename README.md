# openwrt-x86-builder
Manually build openwrt image with Github Actions.

Variable file for variables like "PACKAGES","FILES","ROOTFS_PARTSIZE".

openwrt_branch file for setting specific branch to build.

Variable "PACKAGE" not include language package, so that u can install language package for luci and suggested luci-app all at once via luci.
