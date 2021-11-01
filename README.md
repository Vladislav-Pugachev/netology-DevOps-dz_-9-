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
>> --collector.meminfo

>Disk
>>--collector.diskstats

> Network
>>--collector.netdev 
> 
>>--collector.netstat

### 4.
>[    0.000000] DMI: innotek GmbH VirtualBox/VirtualBox, BIOS VirtualBox 12/01/2006

>[    0.000000] Hypervisor detected: KVM

### 5.
> общесистемное ограничение на количество открытых файлов для всех процессов
>>fs.nr_open = 1048576
```buildoutcfg
vagrant@vagrant:~$ ulimit -n
1024 
```

### 6.
```buildoutcfg
root@vagrant:~# nsenter --target 1828 --pid --mount
root@vagrant:/# ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.0  0.1   9836  4064 pts/1    S    03:40   0:00 /bin/bash
root          10  0.0  0.0   8076   524 pts/1    S+   03:52   0:00 sleep 1h
root          11  1.3  0.1   9836  4028 pts/0    S    03:53   0:00 -bash
root          20  0.0  0.1  11492  3324 pts/0    R+   03:53   0:00 ps aux
```

### 7.

>:(){ :|:& };:
>> Здесь инициализируется функция : которая вызывает саму себя. Пораждаются процессы

>> Срабатывают огрнаичение по количеству процессов для конкретной сессии, можно увеличть ограничнения с помощью ulimit -n 10240 
 
