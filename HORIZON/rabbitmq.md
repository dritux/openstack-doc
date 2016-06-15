# Management and Install RabbitMQ


### User
su rabbitmq


### Port Access

```
4369 (epmd), 25672 (Erlang distribution)  
5672, 5671 (AMQP 0-9-1 without and with TLS)  
15672 (if management plugin is enabled)  
61613, 61614 (if STOMP is enabled)  
1883, 8883 (if MQTT is enabled)  

```

### COMMANDS
```
sudo rabbitmqctl -n rabbit@dri status  

$ rabbitmqctl cluster_status  
$ rabbitmqctl status  
$ sudo service rabbitmq-server status  
$ sudo invoke-rc.d rabbitmq-server start  
$ sudo rabbitmqctl list_exchanges name
$ sudo rabbitmqctl list_queues

$ sudo rabbitmqctl stop_app  
$ sudo rabbitmqctl reset  
$ sudo rabbitmqctl start_app  
$ sudo rabbitmqctl list_users  
```
### Pluign
```
$ sudo rabbitmq-plugins list  
$ sudo rabbitmq-plugins enable rabbitmq_management  
```
### Default access  
```
http://localhost:15672/  
Username: guest  
Password: guest  
```
---

### Install 

- Install rabbit server
```
echo 'deb http://www.rabbitmq.com/debian/ testing main' |
        sudo tee /etc/apt/sources.list.d/rabbitmq.list  

wget -O- https://www.rabbitmq.com/rabbitmq-release-signing-key.asc |
        sudo apt-key add -  

$ sudo apt-get update  
$ sudo apt-get install rabbitmq-server  

```
---
- Install client apt
```
$ sudo vim /etc/apt/sources.list  
deb http://us.archive.ubuntu.com/ubuntu precise main universe  
$ sudo apt-get update  
$ sudo apt-get install rabbitmq-erlang-client  
```
---
- Install client make
```
$ git clone https://github.com/rabbitmq/rabbitmq-erlang-client.git  
$ cd rabbitmq-erlang-client  
$ make  
```


### References
[Management Api](https://cdn.rawgit.com/rabbitmq/rabbitmq-management/rabbitmq_v3_6_2/priv/www/api/index.html)  
[Rabbitmq man](https://www.rabbitmq.com/man/rabbitmqctl.1.man.html)  
