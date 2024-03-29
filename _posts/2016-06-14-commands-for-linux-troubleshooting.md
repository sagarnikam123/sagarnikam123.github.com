---
layout: post
title: "commands for linux troubleshooting (draft)"
description: "imp commands used during troubleshooting"
category: [linux]
tags: [troubleshooting, commands]
---
{% include JB/setup %}

### port

##### Check to see if the server is listening on the host:
```
sudo lsof -i :8080

sudo fuser 9092/tcp
sudo fuser -n tcp 9092

sudo netstat -ant | grep :2181
sudo netstat -peanut | grep ":5140"
```

##### kill process on specific port
```
fuser -k 8080/tcp
kill -9 $(lsof -t -i:8080)

kill -9 $(lsof -t -i:9092)
fuser -k 9092/tcp
```

##### checking port 8080 is open or not
```
cat /etc/services | grep 8080
```

##### connecting to open port
```
sudo yum install telnet
telnet localhost 8080
```

##### scanning port for open port & running services on it
```
sudo yum install nmap
sudo nmap -sT -O localhost
```

---

### permission

##### Changing the ownership of all sub-directories
```bash
sudo chown -R snikam:snikam ./Prod/
```
---

### process

* process id of running program

```
ps aux | grep java
```

* kill prcess with given id

```bash
ps aux | grep -i firefox | awk {'print $2'} | xargs kill -9
```

---

### Shutdown/Restart

* Restart now

```
sudo shutdown -r now
```

* shutdown now (immediately)

```
sudo ?
```

---

### networking

##### Assign static ip

* Check if it is configured

```
sudo ifdown eth0
```

* Edit like this (just the important lines):

```
sudo gedit /etc/network/interfaces

auto eth0
  iface eth0 inet static
  address <static IP address>
  netmask <netmask>
  gateway <default gateway>
  pre-up sleep 2
```

* Activate the new IP

```
sudo ifup eth0
```
---

#### Python
* `ModuleNotFoundError: no module named <X> Error`

```python
import sys
import os

# add dir to PYTHONPATH
sys.path.append(os.getcwd())
```

```python
export PYTHONPATH=${PYTHONPATH}:${HOME}/abcPythonModule 
```

### other

#### vs code - column selction on Mac
```
Shift + option + Command + Right/Left
```
