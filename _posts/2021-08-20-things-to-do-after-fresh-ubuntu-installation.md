---
layout: post
title: "Things to do after fresh Ubuntu installation"
description: "installing min. required softwares"
category: [ubuntu, installation]
tags: [ubuntu, installation, softwares, guide]
---
{% include JB/setup %}


# Things to do after fresh Ubuntu installation

After installing a fresh LTS version of Ubuntu, you need to do a minimum installation of softwares for development or for entertainment purpose. Here is a list for the same

- ##### remove snapstore & make default ubuntu software store

  ```bash
  # check for installed snap packages
  snap list
  # remove snap packages
  sudo snap remove --purge <package-name>
  # remove snap cache
  sudo rm -rf /var/cache/snapd/
  # uninstall snap and snap GUI tool
  sudo apt autoremove --purge snapd gnome-software-plugin-snap
  # clear snap preferences
  sudo rm -fr ~/snap
  ```

- ##### install media codecs & vlc

  ```bash
  sudo apt install ubuntu-restricted-extras
  sudo apt-get update
  sudo apt-get install vlc
  ```

- ##### remove mail client

  ```bash
  sudo apt-get purge thunderbird*
  ```

- ##### install package updates

  ```bash
  sudo apt-get update && sudo apt-get dist-upgrade
  ```

- ##### download from sites

  - [Google Chrome](https://www.google.com/chrome/)
  - [Visual studio code](https://code.visualstudio.com/download)
  - [Dropbox](https://www.dropbox.com/install-linux)
  - [Eclipse](https://www.eclipse.org/downloads/packages/)
  - [Oracle Java JDK (LTS)](https://www.oracle.com/java/technologies/javase-downloads.html)
  - [Jetbrains Toolbox](https://www.jetbrains.com/toolbox-app/)

- ##### install & configure (export path variables to .bashrc)

  - Java

    ```bash
    sudo mkdir /usr/lib/jvm/
    sudo tar -xvzf jdk-11.0.12_linux-x64_bin.tar.gz -C /usr/lib/jvm/
    # path
    export JAVA_HOME=/usr/lib/jvm/jdk-11.0.12
    export PATH=$PATH:$JAVA_HOME/bin
    ```

  - Gradle

    ```bash
    sudo mkdir /opt/gradle
    sudo unzip -d /opt/gradle gradle-7.2-bin.zip
    # path
    export PATH=$PATH:/opt/gradle/gradle-7.2/bin
    ```

  - Go

    ```bash
    sudo tar -xvzf go1.16.4.linux-amd64.tar.gz -C /usr/local/
    # path
    export GOROOT=/usr/local/go
    export GOPATH=$HOME/go
    export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
    ```

- ##### install additional archieve utilities

  ```bash
  sudo apt install rar unrar p7zip-full p7zip-rar
  ```


- ##### install gnome tweaks

  ```bash
  sudo apt install gnome-tweaks
  ```

- ##### install Markdown (Typora)

  ```bash
  wget -qO - https://typora.io/linux/public-key.asc | sudo apt-key add -
  # add Typora's repository
  sudo add-apt-repository 'deb https://typora.io/linux ./'
  sudo apt-get update
  # install typora
  sudo apt-get install typora
  ```
  
- ##### other to do things

    - enable Night Light mode (Settings - > Display -> Night Light tab)
    - select default apps (Settings -> Default Applications)
    - connect to online account (Ubuntu one, Settings -> Online Accounts)
    - add your favorite apps to the dock
