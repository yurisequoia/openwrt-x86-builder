# openwrt-x86-builder
Manually build openwrt image with Github Actions.

Variable file for variables like "PACKAGES","FILES","ROOTFS_PARTSIZE".

openwrt_branch file for setting specific branch to build.

The APK-based ImageBuilder installs `tailscale@snapshot` using the tagged USTC snapshot repository in `files/etc/apk/repositories.d/customfeeds.list`. The workflow appends this file to ImageBuilder's `repositories` before installing packages and passes `CONFIG_SIGNATURE_CHECK=` to allow untrusted packages during the build.

The image also includes the snapshot repository and `allow-untrusted` in `/etc/apk/config` for package installation and updates after flashing. This disables APK signature verification; snapshot packages and their dependencies must remain compatible with the selected OpenWrt release.

Variable "PACKAGE" not include language package, so that u can install language package for luci and suggested luci-app all at once via luci.
