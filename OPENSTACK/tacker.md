# Tacker
- Mitaka: VIM mult site
- Multi-VIM Type Support sites: OpenStack, VMware ESXi, AWS or Custom


### Install devstack
```
enable_plugin tacker https://github.com/openstack/tacker
```

### Passos
* 1 - Criar catálog - Template Tosca
* 2 - Criar instância - Selecionar catálogo
* 3 - Cria VIM

### Template TOSCA é possível
* Configurar regras de firewall
* Setar disco, memória ,cpu
* Setar interface de rede
* Executar script bash
* Deployment de imagens via url (VNFImage)
* Setar chaves ssh no template
* Monitorar serviços (VNFMonitorPing)
* Tratamento quando um evento ocorre, restabelecer ou log

### Features provided by Tacker:
* VNF Catalog – repository of VNF descriptors (VNFDs) in a database
* VNF lifecycle management - VNF Instantiation and Termination
* Refined Management and Orchestration (MANO) API
* VNF Monitoring - Health and Performance Indicators 
* Parameterized topology and orchestration specification for cloud applications (TOSCA) VNF definition template
* VNF user-data injection
* VNF configuration injection - during instantiation and update
* Loadable health monitoring framework
---

### Drivers
OpenWRT, 

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


### COMMANDS
```
tacker bash-completion     Prints all of the commands and options for bash-completion.
tacker ext-list            List all extensions.
tacker ext-show            Show information of a given resource.
tacker help                print detailed help for another command
tacker vim-delete          Delete a given VIM.
tacker vim-list            List VIMs that belong to a given tenant.
tacker vim-register        Create a VIM.
tacker vim-show            Show information of a given VIM.
tacker vim-update          Update a given VIM.
tacker vnf-create          Create a VNF.
tacker vnf-delete          Delete a given VNF.
tacker vnf-list            List VNF that belong to a given tenant.
tacker vnf-show            Show information of a given VNF.
tacker vnf-update          Update a given VNF.
tacker vnfd-create         Create a VNFD.
tacker vnfd-delete         Delete a given VNFD.
tacker vnfd-list           List VNFD that belong to a given tenant.
tacker vnfd-show           Show information of a given VNFD.
tacker vnfd-template-show  Show template of a given VNFD.


tacker vnfd-create --vnfd-file=tosca_openwrt_vnfd.yaml --name=demo-vnf

```


### References:
* GIT
[GIT Summit](https://github.com/yamahata/)  
[GIT OPNFV](https://github.com/opnfv)   

* DOCS
[Wiki](https://wiki.openstack.org/wiki/Tacker)  
[OPNFV](https://www.opnfv.org/software)  
[API](http://tacker-docs.readthedocs.io/en/latest/devref/mano_api.html)  
[Tacker Roadmap](https://etherpad.openstack.org/p/tacker-mitaka-priorities)  
[Tacker Docs](http://tacker-docs.readthedocs.org/en/latest/index.html)  
[Tacker Monitor](http://docs.openstack.org/developer/tacker/devref/monitor-api.html)


* PDF
[ETSI NFV OVERVIEW](http://www.ietf.org/proceedings/88/slides/slides-88-opsawg-6.pdf)  
[ETSI GS NFV-MAN](http://www.etsi.org/deliver/etsi_gs/NFV-MAN/001_099/001/01.01.01_60/gs_nfv-man001v010101p.pdf)  

* VIDEOS
[Tacker vBrownBag](https://www.youtube.com/watch?v=y9fYiIsIErc)
[Tacker Demo](https://www.youtube.com/watch?v=EfqWArz25Hg)


