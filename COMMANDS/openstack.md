# COMMANDS

### SERVICES
```
systemctl restart openstack-keystone.service
openstack-service status openstack-keystone
openstack-service status openstack-keystone
sudo service rabbitmq-server status

```

### NETWORK

	nmap -sT -O localhost
	netstat -anp | grep 80
	hostname -s
	
### OPENSTACK

### Commands lists
	openstack domain list
	openstack service list
	openstack project list --long --quote none -f csv

### Commands create
	openstack credential create --data '{"access": <access>, "secret": <secret>}'
	openstack service create image --name=teste

### Create a new endpoint associated with a service.
	openstack service create image --name=teste
	openstack endpoint create teste public http://localhost:5000
	openstack endpoint create teste public http://localhost:5000 --region RegionOne
	openstack endpoint list --interface=admin

### Command param example
	openstack --os-url http://localhost:5000/v3 --os-identity-api-version 3 --os-token=ADMIN role create admin
	openstack --os-url http://localhost:5000/v3 --os-identity-api-version 3 --os-token=ADMIN role add --user u1 --project default admin

