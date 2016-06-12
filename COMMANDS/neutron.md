# Neutron
> Network management commands

### Command view compute node  
```
$ ip -o l sh|awk '{print $2}'  
$ ip -o l sh tap9684b07e-62  
$ brctl show # show bridges  
$ ip -d l sh qvb9684b07e-62  
$ sudo ovs-vsctl show  # show all interface attach openvswitch  
$ sudo ovs-ofctl dump-flows br-in  
$ sudo ovs-ofctl show br-int  
$ sudo ovs-ofctl dump-flows br-ex  
$ ip netns list # list namespace  
---
```
- run within the namespace  
```
$ sudo ip netns exec qdhcp-5ce5aff5-8d18-4a5e-bae0-4b1fe97e998c ip a s  
$ sudo ip netns exec qdhcp-5ce5aff5-8d18-4a5e-bae0-4b1fe97e998c ifconfig  
$ sudo ip netns exec qdhcp-5ce5aff5-8d18-4a5e-bae0-4b1fe97e998c netstat -ltnpu  
```

---
- Nat table  
```
$ sudo ip netns exec qdhcp-5ce5aff5-8d18-4a5e-bae0-4b1fe97e998c iptables -t nat -nL  
```
---

- Ping router icmp  
```
$ sudo ip netns exec qrouter-d97396a0-0508-4554-9d85-83c47f55d146 ping 10.0.0.3  
```
> to release the icmp set in Access & Security   
---

- Access ssh with private ip  
```
$ sudo ip netns exec qrouter-d97396a0-0508-4554-9d85-83c47f55d146 ssh cirros@10.0.0.3 
``` 
> to release the ssh set in Access & Security  
---
- Associate floating ip and access ssh  
> Instance >  Associate Floating IP > Added public ip address > Associate  
``` 
$ ssh cirros@172.24.4.4  
```

```
No instance

lo:
eth0:
wlan0:
ovs-system:
br-ex:
br-int:
br-tun:
tun0:
virbr0:
```
```
Create instance

lo:
eth0:
wlan0:
ovs-system:
br-ex:
br-int:
br-tun:
tun0:
virbr0:
qbr9684b07e-62:
qvo9684b07e-62:
qvb9684b07e-62: 
tap9684b07e-62:
```

### Terms explained below based on my understanding  
- qvo: veth pair openvswitch side
- qvb: veth pair bridge side
- qbr: bridge linux
- qr: l3 agent managed port, router side
- qg: l3 agent managed port, gateway side
- tap: interface virtual machine - eth0 in virtual machine
- qrouter: Virtual router
- qdhcp: Virtual network 

# References:

[Under the hood: networking](https://github.com/lorin/openstack-hackspace/blob/master/under-the-hood-network.md)

