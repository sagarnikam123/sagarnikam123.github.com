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
lsof -i :8080
sudo netstat -peanut | grep ":5140"
```

---

### process

```
ps aux | grep java
```

---

#### Shutdown/Restart

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
