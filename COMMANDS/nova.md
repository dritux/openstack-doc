# Nova
> Nova management commands  

$ openstack hypervisor list  
$ openstack hypervisor show HypervisorName


- List instances, check status of instance  
    $ nova list  

- List images  
    $ openstack image list  

- List flavors  
    $ openstack flavor list   

- List Networks  
    $ openstack network list  

- Create instance  
    $  nova boot --image 1325bd4f-773f-4a2e-bea3-7930e93a0dbb --flavor m1.tiny debian --nic net-id=NetworkID  

    $  nova boot --image 1325bd4f-773f-4a2e-bea3-7930e93a0dbb --flavor m1.tiny debian  

- Show instance create  
    $ nova show <name>  

- Delete instance  
    $ nova delete <name>  

- View console log the instance  
    $ nova console-log <name>  

---
### Pause, suspend, stop, rescue, resize, rebuild, reboot an instance
- Pause
    $ nova pause <name>  
    $ nova pause volumeTwoImage$   

- Unpause  
    $ nova unpause <name>  

- Suspend  
    $ nova suspend <name>  

- Unsuspend  
    $ nova resume <name>  

- Stop  
    $ nova stop <name>  

- Start  
    $ nova start <name>  

- Rescue  
    $ nova rescue <name>  

- Resize
    $ nova resize <name> <flavor>  
    $ nova resize my-pem-server m1.small  
    $ nova resize-confirm server1  

- Rebuild
    $ nova rebuild <name> <image>  
    $ nova rebuild newtinny cirros-qcow2  

- Reboot
    $ nova reboot <name>  
    $ nova reboot newtinny  

---

### Inject a keypair into an instance and access the instance with that keypair

- Create keypair  
    $ nova keypair-add test > test.pem  
    $ chmod 600 test.pem  

- Boot
    $ nova boot --image cirros-0.3.0-x86_64 --flavor m1.small --key_name test my-first-server  

- ssh into instance
    $ sudo ip netns exec qdhcp-98f09f1e-64c4-4301-a897-5067ee6d544f ssh -i test.pem cirros@10.0.0.4  

- Set metadata on an instance  
    $ nova meta volumeTwoImage set newmeta="my meta data"  

- Create an instance snapshot  
    $ nova image-create volumeTwoImage snapshotOfVolumeImage  
    $ nova image-show snapshotOfVolumeImage  

### Manage security groups
> Add rules to default security group allowing ping and ssh between #instances in the default security group  

    $ nova secgroup-add-group-rule default default icmp -1 -1  
    $ nova secgroup-add-group-rule default default tcp 22 22  


#### Attach volume to instance after instance is active, and volume is available  
    $ nova volume-attach <instance-id> <volume-id> auto  
    $ nova volume-attach MyVolumeInstance /dev/vdb auto  


# References

[OpenStack command-line interface cheat sheet](http://docs.openstack.org/user-guide/cli_cheat_sheet.html)  
[OpenStack Command Line Cheat Sheet](http://anystacker.com/2014/02/openstack-command-line-cheat-sheet)  
