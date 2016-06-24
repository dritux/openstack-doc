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
* ETSI - European Telecommunications Standards Institute
* SDN - Redes definidas por software
* NFV - Virtualização de funções de rede

* OPENMANO - Telefonica - base ETSI MANO
* Tacker - Openstack - Base ETSI MANO and TOSCA YAML
* OPNFV - Openstack - ETSI - OpenContrail - OpenDaylight


### OTHERS

* ASTARA
```
Astara provides OpenStack operators with a vendor-agnostic network orchestration platform that addresses the
complex nature and scale of Neutron implementations. Astara features a driver-based orchestrator to manage
network functions from different providers on bare metal, in virtual machines (VMs) and containers.
```

* OPNFV
```
Open Platform for NFV (OPNFV) provides an open source platform for deploying NFV solutions that leverages investments from a community of developers and solution providers. The investments are designed to enable interoperability across a broad set of industry players and usage models. The goal is to create a framework that addresses the needs of the platform providers, application developers and end users who will be required to operate and maintain these complex systems.
```

* Tacker - OpenStack NFV Orchestration
```
Tacker is an official OpenStack project building a Generic VNF Manager (VNFM) and a NFV Orchestrator (NFVO) to deploy and operate Network Services and Virtual Network Functions (VNFs) on an NFV infrastructure platform like OpenStack. It is based on ETSI MANO Architectural Framework and provides a functional stack to Orchestrate Network Services end-to-end using VNFs.
```


### References:

[GIT Summit](https://github.com/yamahata/)
[GIT OPNFV](https://github.com/opnfv)

[Wiki Tacker](https://wiki.openstack.org/wiki/Tacker)
[Tacker](http://tacker-docs.readthedocs.io/en/latest/)

[OPNFV](https://www.opnfv.org/software)
[OPNFV NEWS](https://www.opnfv.org/news-faq/press-release/2016/03/opnfv-delivers-second-release-open-source-network-functions)

