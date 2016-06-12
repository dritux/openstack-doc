# Glance
> Image management commands


$ source admin-openrc-v2.sh
$ openstack image list
$ openstack image show cirros-0.3.4-x86_64-uec
 

### Image create qcow2

$ glance image-create --name=debian64-image --disk-format=qcow2 --container-format=bare --visibility=public --file ./image/debian-8.5.0-openstack-amd64.qcow2

### Image delete
$ glance image-delete IMAGEID  
$ openstack image delete debian64-image  

### Image update
$ glance image-update IMAGE  