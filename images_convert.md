# CONVERT IMAGES

### DEPENDENCY
	$ sudo apt-get install qemu-kvm qemu virt-manager virt-viewer libvirt-bin

### Create a blank disc image
	$ qemu-img create -f qcow2 ubuntu.img 3G

### Create images
	$ qemu-system-x86_64 -m 256 -hda ubuntu.img -cdrom ubunbu-16-2.iso -boot d

### Convert image img to qcow2
	$ qemu-img convert -O qcow2 ubuntu.img ubuntu.qcow2

### Convert image qcow2 to img
	$ qemu-img convert ubuntu.qcow2 -O raw ubuntu.img

### Convert a QCOW2, RAW, VMDK or VDI image to VHD
	$ qemu-img convert source.img -O vpc -o subformat=dynamic dest.vhd

### Convert a QCOW2, RAW, VMDK or VDI image to VHDX
	$ qemu-img.exe convert source.img -O vhdx -o subformat=dynamic dest.vhdx

### Check a virtual disk for consistency
	$ qemu-img check ubuntu.qcow2 

### Get info about a virtual disk
	$ qemu-img info image.qcow2	


# SOFTWARE
- virt-manager
- virtualbox


# COMMAND VIRSH
	$ virsh

```
virsh # list --all
 Id    Nome                           Estado
--------------------------------------------------
```


# REFERENCES

[Wiki convert formats](https://en.wikibooks.org/wiki/QEMU/Images)  
[Convert kvm-pxe](https://www.ibm.com/developerworks/community/wikis/home?lang=en#!/wiki/OpenStack/page/Creating+qcow2+CentOS+Image+for+OpenStack)  
[Virt Commands](http://virt-tools.org/learning/install-with-command-line/)  
[Pfsense Images](http://mirror.transip.net/pfsense/downloads/)  
[Ubuntu Images](http://cloud-images.ubuntu.com/trusty/current/)  
[Debian Images](http://cdimage.debian.org/cdimage/openstack/current/)  
[Windows Image](https://cloudbase.it/downloads/qemu-img-win-x64-2_3_0.zip)  
[Docs qemu](http://qemu.weilnetz.de/qemu-doc.html)  
