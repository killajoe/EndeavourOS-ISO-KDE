# joekamprad-KDE-ISO

[![Maintenance](https://img.shields.io/maintenance/yes/2023.svg)]()

![joekamprad-kde-iso](https://user-images.githubusercontent.com/16797647/221051625-d4f292c6-8801-47bc-863c-498592cb486a.jpg)

* Personal Edition of the EndeavourOS ISO using KDE as Livesession and for offline installs.
* It will gbet rebuilded every 3 days.

### Development source

- [EndeavourOS-ISO source](https://github.com/endeavouros-team/EndeavourOS-ISO) (Live environment with XFCE4-Desktop)
- [EndeavourOS-calamares](https://github.com/endeavouros-team/calamares) (installer framework)


### Base source

- [Arch-ISO](https://gitlab.archlinux.org/archlinux/archiso)
- [Calamares](https://github.com/calamares/calamares)

# Lates autobuilds will be uploaded here:
http://endeavour.kamprad.net/develiso/

# How to build ISO

You need to use an installed EndeavourOS system or any archbased system with EndeavourOS [repository](https://github.com/endeavouros-team/mirrors) enabled.

As the installer packages and needed dependencies will get installed from EndeavourOS repository.


**Install build dependencies**

```
sudo pacman -S archiso mkinitcpio-archiso git squashfs-tools --needed
```
Recommended to reboot after this changes.

**get the code:**


```
git clone https://github.com/killajoe/EndeavourOS-ISO-KDE.git
cd EndeavourOS-ISO-KDE
./prepare.sh
```

**build:**

~~~
sudo ./mkarchiso -v "."
~~~

**with log:**

~~~
sudo ./mkarchiso -v "." 2>&1 | tee "eosiso_$(date -u +'%Y.%m.%d-%H:%M').log"
~~~

**The .iso appears in `out` directory**


### Advanced
To install locally builded packages on ISO put the packages inside directory:

~~~
airootfs/root/packages
~~~

Packages will get installed and directory will be cleaned up after that.
