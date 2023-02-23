# joekamprad-KDE-ISO

[![Maintenance](https://img.shields.io/maintenance/yes/2023.svg)]()



### Development source

- [EndeavourOS-ISO source](https://github.com/endeavouros-team/EndeavourOS-ISO) (Live environment with XFCE4-Desktop)
- [EndeavourOS-calamares](https://github.com/endeavouros-team/EndeavourOS-calamares) (installer framework)


### Base source

- [Arch-ISO](https://gitlab.archlinux.org/archlinux/archiso)
- [Calamares](https://github.com/calamares/calamares)



# Boot options

Systemd-boot for UEFI systems:  
<img src="https://raw.githubusercontent.com/endeavouros-team/screenshots/master/Apollo/apollo-systemdboot.png" alt="drawing" width="600"/>

Bios-boot (syslinux) for legacy systems:  
<img src="https://raw.githubusercontent.com/endeavouros-team/screenshots/master/Apollo/apollo-syslinux.png" alt="drawing" width="600"/>



# How to build ISO

You need to use an installed EndeavourOS system or any archbased system with EndeavourOS [repository](https://github.com/endeavouros-team/mirrors) enabled.

As the installer packages and needed dependencies will get installed from EndeavourOS repository.


### Install build dependencies

```
sudo pacman -S archiso mkinitcpio-archiso git squashfs-tools --needed
```
Recommended to reboot after this changes.

###  Build

~~~
sudo ./mkarchiso -v "."
~~~

**or with log:**

~~~
sudo ./mkarchiso -v "." 2>&1 | tee "eosiso_$(date -u +'%Y.%m.%d-%H:%M').log"
~~~

##### 3. The .iso appears in `out` directory


## Advanced

To install locally builded packages on ISO put the packages inside directory:

~~~
airootfs/root/packages
~~~

Packages will get installed and directory will be cleaned up after that.
