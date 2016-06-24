# Tacker


### Features provided by Tacker:
* VNF catalog
* VNF lifecycle management
* Refined Management and Orchestration (MANO) API
* Parameterized topology and orchestration specification for cloud applications (TOSCA) VNF definition template
* VNF user-data injection
* VNF configuration injection - during instantiation and update
* Loadable health monitoring framework
---

### Catalog
* Repository of VNF Descriptors (VNFD)
* VNF definition using TOSCA templates
* Support for multiple VMs per VNF (VDUs)
* Tacker APIs to on-board and maintain VNF Catalog
* VNFD are stored in Tacker DB
---

### VNFD using TOSCA
* Glance image IDs
* Nova properties - Placement, CPU pinning, NUMA policy, etc
* Auto-Scaling Policy
* Performance Monitoring Policy
* Auto-Healing Policy

---
### VNF Manager - Horizon
* Ericssion IMS Server (EPG)
* Brocade Vyata 5600 Virtual Router (Routing)
* Cisco CSR1000v Virtual Router (VPN)
* Palo Alto Virtual Firewall (IDS)
* OpenWRT with services (Firewall)

---
### Key features Mitaka:
* Tacker Multi-Site allows Operators to place, manage and monitor VNFs in multiple OpenStack Clouds
* Tacker Service Function Chaining API for a VNF level service-chaining backed by an SDN Controller
* TOSCA Parser integration brings industry's first OASIS NFV Profile Standards based TOSCA Orchestrator
* Enhanced VNF Placement placing VNFs the most efficient way with CPU-Pinning, NUMA topology awareness, etc

### Glossary:

* NFV - Network Function Virtualization
* VIM - Virtual infrastructure manager
* OPNFV - Open Platform for Network Function Virtualization
* VNFM - VNF Manager
* NFVO - NFV Orchestrator



### References:
[GIT Summit](https://github.com/yamahata/)  
[GIT OPNFV](https://github.com/opnfv)   

[Wiki](https://wiki.openstack.org/wiki/Tacker)  
[OPNFV](https://www.opnfv.org/software)  
