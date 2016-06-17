# Configure mistral

### Install in devstack
```
enable_plugin mistral https://github.com/openstack/mistral
```

### API
- endpoint: http://localhost:8989/v2

```
GET, POST, PUT, DELETE

http://{{IP}}:8989/v2/workbooks
http://{{IP}}:8989/v2/workflows
http://{{IP}}:8989/v2/executions
http://{{IP}}:8989/v2/actions
http://{{IP}}:8989/v2/tasks
http://{{IP}}:8989/v2/action_executions
http://{{IP}}:8989/v2/cron_triggers
http://{{IP}}:8989/v2/environments
http://{{IP}}:8989/v2/services

POST --> http://{{IP}}:8989/v2/workbooks/validation

```

References:
[Status code](https://github.com/for-GET/know-your-http-well/blob/master/status-codes.md)  
[Api](http://docs.openstack.org/developer/mistral/developer/webapi/v2.html)  
[Template example](https://github.com/openstack/mistral-extra)  
[DSL](http://docs.openstack.org/developer/mistral/dsl/dsl_v2.html)  
[Mistral template full](https://wiki.openstack.org/wiki/Mistral/DSLv1)  
[Git template calculator](https://github.com/openstack/mistral-extra/blob/master/examples/v2/calculator/calculator.yaml)  
