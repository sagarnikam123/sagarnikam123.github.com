---
layout: post
title: "Things to do after fresh MacOS installation"
description: "installing min. required softwares"
category: [mac, macos, installation]
tags: [mac, installation, softwares, guide]
---
{% include JB/setup %}


After installing a fresh version of MacOS installation, you need to do a minimum installation of softwares for development or for entertainment purpose. Here is a list for the same

- macOS version

  ```
  sw_vers
  ```

  ```
  system_profiler SPSoftwareDataType
  ```

  ```
  uname -a
  ```

- install **[Homebrew](https://brew.sh/)** - a package manager for mac

  ```
  /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
  ```

- install **[MacPorts](https://www.macports.org/install.php)**

  ```bash
  sudo port selfupdate # to update port
  port installed # all installed ports
  port outdated # list of outdated ports
  port upgrade vim # upgrade installed port
  ```

- create **.zshrc** file in home directory

  ```bash
  nano ~/.zshrc
  ```

- install **xcode command-line tools** (it prompts to install)

  ```bash
  git --version
  ```

- **download from sites**

  - [Google Chrome](https://www.google.com/chrome/)
  - [Firefox](https://www.mozilla.org/en-US/firefox/mac/)
  - [Visual studio code](https://code.visualstudio.com/download)
  - [Atom](https://atom.io/)
  - [Jetbrains Toolbox](https://www.jetbrains.com/toolbox-app/) (PyCharm & IntelliJ)
  - [Eclipse](https://www.eclipse.org/downloads/packages/)
  - [Slack](https://slack.com/intl/en-in/downloads/mac)
  - [Zoom client](https://zoom.us/download)
  - [Skype](https://www.skype.com/en/get-skype/download-skype-for-desktop/)
  - [Dropbox](https://www.dropbox.com/downloading)
  - [RStudio](https://www.rstudio.com/products/rstudio/download/)
  - [MySQL JDBC connector](https://dev.mysql.com/downloads/connector/j/)
  - [R](https://cran.r-project.org/bin/macosx/)
  - [Zettlr](https://www.zettlr.com/) (Markdown editor)

- **install & configure (export path variables to .bashrc)**

  - [Oracle Java JDK (LTS)](https://www.oracle.com/java/technologies/javase-downloads.html)

    ```bash
    # JAVA_HOME
    export JAVA_HOME=$(/usr/libexec/java_home)
    export PATH=$PATH:$JAVA_HOME/bin

    # export JAVA_HOME=/Library/Java/JavaVirtualMachines/jdk-11.0.14.jdk/Contents/Home
    ```

  - [Go](https://go.dev/dl/)

    ```bash
    # GOROOT & GOPATH
    export GOROOT=/usr/local/go
    export GOPATH=$HOME/go
    export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
    ```

- **configure git**

  - [create a personal access token](https://docs.github.com/en/github/authenticating-to-github/keeping-your-account-and-data-secure/creating-a-personal-access-token)

    ```bash
    git config --global user.email <you@example.com>
    git config --global user.name <Your Name>
    ```

  - configure [git credential manager core](https://github.com/microsoft/Git-Credential-Manager-Core/) for PAT (Personel Access Token)

    ```bash
    # tell Git you want to store credentials in the osxkeychain
    git config --global credential.helper osxkeychain

    # add your access token to the osxkeychain- by using pull/push
    # when prompted for password, instead enter access token(it get cached in the osxkeychain automatically)
    git clone https://github.com/username/repo.git
      ```

- **install & configure open-ssh**

  ```bash
  sudo port install openssh
  sudo port load openssh
  ```
- **install/uninstall with brew**

  ```bash
  brew install wget
  brew list # lists apps installed by brew
  brew uninstall wget
  ```
- **containers & kubernetes** (docker without _Docker Desktop_)
  - install [Rancher Desktop](https://rancherdesktop.io/) (it install below items by default/choice)
    - *container runtime* of your choice (containerd or dockerd) - free
    - kubernetes, Traefik
    - docker(cli), docker-compose, docker-buildx
    - kubectl, helm, nerdctl, rdctl
