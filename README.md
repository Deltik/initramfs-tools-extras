# Extra Features for initramfs-tools
You can add these hooks and scripts to your initramfs-tools to have support for bond interfaces or VLAN interfaces during boot.
After copying the relevant files into `/etc/initramfs-tools`, bonding and VLANs options can be added to your `/etc/initramfs-tools/initramfs.conf`.

## Installation
Copy the files in `./etc/initramfs-tools` to the corresponding folder on your system (`/etc/initramfs-tools`).
Ensure the hooks and scripts are executable, if they are not already.

### Add VLAN Interface
Add the following line to your `/etc/initramfs-tools/initramfs.conf` to configure VLAN IDs 221 and 222 on eth0:

```
VLAN="eth0:221 eth0:222"
```

### Add Bond Interface
Add the following line to your `/etc/initramfs-tools/initramfs.conf` to enslave eth0 and eth1 to bond0 and eth2 and eth3 to bond1.

```
BOND="bond0:eth0,eth1 bond1:eth2,eth3"
```

With the following line you can also set the [bonding driver options](https://wiki.linuxfoundation.org/networking/bonding#bonding_driver_options):

```
BOND_MODE="mode=802.3ad miimon=100"
```
