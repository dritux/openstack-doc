# COMMANDS


### Image create qcow2
$ curl -O https://www.mirrorservice.org/sites/dl.fedoraproject.org/pub/fedora/linux/releases/23/Cloud/x86_64/Images/Fedora-Cloud-Base-23-20151030.x86_64.qcow2

$ glance --os-image-api-version 2 image-create --name 'Fedora-23-x86_64' --disk-format qcow2 --container-format bare --file Fedora-Cloud-Base-23-20151030.x86_64.qcow2

$ glance image-create --name F20-x86_64 --disk-format qcow2 --container-format bare --is-public True < fedora-image.qcow2