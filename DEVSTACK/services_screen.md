##COMMANDS

###LOGS
```
$ sudo tail -f /var/log/apache2/horizon_error.log & echo $! >/opt/stack/status/stack/horizon.pid; fg || echo "horizon failed to start" | tee "/opt/stack/status/stack/horizon.failure"
```

```
$ sudo tail -f /var/log/apache2/keystone.log & echo $! >/opt/stack/status/stack/key.pid; fg || echo "key failed to start" | tee "/opt/stack/status/stack/key.failure"
```

```
$ sudo tail -f /var/log/apache2/keystone_access.log & echo $! >/opt/stack/status/stack/key-access.pid; fg || echo "key-access failed to start" | tee "/opt/stack/status/stack/key-access.failure"
```
###STATS
```
$ /home/stack/www/devstack/tools/dstat.sh /opt/stack/logs & echo $! >/opt/stack/status/stack/dstat.pid; fg || echo "dstat failed to start" | tee "/opt/stack/status/stack/dstat.failure"
```

###CINDER
```
$ /usr/local/bin/cinder-api --config-file /etc/cinder/cinder.conf & echo $! >/opt/stack/status/stack/c-api.pid; fg || echo "c-api failed to start" | tee "/opt/stack/status/stack/c-api.failure"
```

```
$ /usr/local/bin/cinder-volume --config-file /etc/cinder/cinder.conf & echo $! >/opt/stack/status/stack/c-vol.pid; fg || echo "c-vol failed to start" | tee "/opt/stack/status/stack/c-vol.failure"
```

```
$ /usr/local/bin/cinder-scheduler --config-file /etc/cinder/cinder.conf & echo $! >/opt/stack/status/stack/c-sch.pid; fg || echo "c-sch failed to start" | tee "/opt/stack/status/stack/c-sch.failure"
```

###GLANCE
```
$ /usr/local/bin/glance-registry --config-file=/etc/glance/glance-registry.conf & echo $! >/opt/stack/status/stack/g-reg.pid; fg || echo "g-reg failed to start" | tee "/opt/stack/status/stack/g-reg.failure"
```

```
$ /usr/local/bin/glance-api --config-file=/etc/glance/glance-api.conf & echo $! >/opt/stack/status/stack/g-api.pid; fg || echo "g-api failed to start" | tee "/opt/stack/status/stack/g-api.failure"
```
###NOVA
```
$ sg libvirtd '/usr/local/bin/nova-compute --config-file /etc/nova/nova.conf' & echo $! >/opt/stack/status/stack/n-cpu.pid; fg || echo "n-cpu failed to start" | tee "/opt/stack/status/stack/n-cpu.failure"
```

```
$ /usr/local/bin/nova-conductor --config-file /etc/nova/nova.conf & echo $! >/opt/stack/status/stack/n-cond.pid; fg || echo "n-cond failed to start" | tee "/opt/stack/status/stack/n-cond.failure"
```

```
$ /usr/local/bin/nova-consoleauth --config-file /etc/nova/nova.conf & echo $! >/opt/stack/status/stack/n-cauth.pid; fg || echo "n-cauth failed to start" | tee "/opt/stack/status/stack/n-cauth.failure"
```

```
$ /usr/local/bin/nova-novncproxy --config-file /etc/nova/nova.conf --web /opt/stack/noVNC & echo $! >/opt/stack/status/stack/n-novnc.pid; fg || echo "n-novnc failed to start" | tee "/opt/stack/status/stack/n-novnc.failure"
```

```
$ /usr/local/bin/nova-scheduler --config-file /etc/nova/nova.conf & echo $! >/opt/stack/status/stack/n-sch.pid; fg || echo "n-sch failed to start" | tee "/opt/stack/status/stack/n-sch.failure"
```

```
$ /usr/local/bin/nova-network --config-file /etc/nova/nova.conf & echo $! >/opt/stack/status/stack/n-net.pid; fg || echo "n-net failed to start" | tee "/opt/stack/status/stack/n-net.failure"
```

```
$ /usr/local/bin/nova-api & echo $! >/opt/stack/status/stack/n-api.pid; fg || echo "n-api failed to start" | tee "/opt/stack/status/stack/n-api.failure"

```
