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


### REFERENCES

[Wiki convert formats](https://en.wikibooks.org/wiki/QEMU/Images)  
[Convert kvm-pxe](https://www.ibm.com/developerworks/community/wikis/home?lang=en#!/wiki/OpenStack/page/Creating+qcow2+CentOS+Image+for+OpenStack)  
[Virt Commands](http://virt-tools.org/learning/install-with-command-line/)  
[Pfsense Images](http://mirror.transip.net/pfsense/downloads/)  
[Ubuntu Images](http://cloud-images.ubuntu.com/trusty/current/)  
[Debian Images](http://cdimage.debian.org/cdimage/openstack/current/)  
[Cloudbase Windows Image](https://cloudbase.it/windows-cloud-images/#download)  
[Docs qemu](http://qemu.weilnetz.de/qemu-doc.html)  
[Cloudbase](https://cloudbase.it/euladownload.php?h=kvm)  
[Create image for openstack](http://docs.openstack.org/image-guide/create-images-automatically.html)  
[Create windows image for openstack](https://poolsidemenace.wordpress.com/2011/06/16/porting-windows-to-openstack/)  

### Download Images for tests

[Cirros 64 - Format img](http://download.cirros-cloud.net/0.3.4/cirros-0.3.4-x86_64-disk.img)  
[Ubuntu 64 - Format img](http://uec-images.ubuntu.com/trusty/current/trusty-server-cloudimg-amd64-disk1.img)  
[Debian 64 - Format qcow2](http://cdimage.debian.org/cdimage/openstack/current/debian-8.5.0-openstack-amd64.qcow2)  
[Debian 64 - Format raw](http://cdimage.debian.org/cdimage/openstack/current/debian-8.5.0-openstack-amd64.raw)  
[Centos 64 - Format qcow2](http://cloud.centos.org/centos/7/images/CentOS-7-x86_64-GenericCloud-1605.qcow2)  
[Opensuse 64 - Format qcow2](http://download.opensuse.org/repositories/Cloud:/Images:/openSUSE_13.2/images/openSUSE-13.2-OpenStack-Guest.x86_64.qcow2)  
[Redhat 64 - Format qcow2](http://c250663.r63.cf1.rackcdn.com/rhel56_x86_64.qcow2)  
[Windows 64](https://cloudbase.it/downloads/qemu-img-win-x64-2_3_0.zip)   



