### 1.
>/etc/systemd/system/node_exporter.service
```buildoutcfg
[Unit]
Description=Node Exporter

[Service]
EnvironmentFile=/home/vagrant/node_exporter/node_exporter_option
ExecStart=/home/vagrant/node_exporter/node_exporter $EXTRA_OPTS

[Install]
WantedBy=multi-user.target
```
### 2.

>CPU
>>--collector.cpu.info
>Memory
>> 