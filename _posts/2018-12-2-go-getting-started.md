---
layout: post
title: "Go getting started (draft)"
description: "From Golang installtion, code, tools, etc"
category: [learning,programming, go]
tags: [golang, gotools, gpextension,]
---
{% include JB/setup %}

- #### install & configure

  - [go download](https://golang.org/dl/)

      - ```bash
        # extract
        sudo tar -xvzf go1.16.4.linux-amd64.tar.gz -C /usr/local/
        ```
  - export path

      - ```bash
        export GOROOT=/usr/local/go
        export GOPATH=$HOME/go
        export PATH=$PATH:$GOROOT/bin:$GOPATH/bin
        ```

- #### packages/extension

  - **For Text editors**

    - [gocode](https://godoc.org/golang.org/x/tools/cmd/guru) - autocompletion for Go in text editors

      - ```
        go get -u github.com/nsf/gocode
        ```

    - [guru](https://godoc.org/golang.org/x/tools/cmd/guru) - a tool for answering questions about Go source code (for goclipse/Eclipse)

      - ```
        go get -u golang.org/x/tools/cmd/guru 
        ```

      - For Visual Studio -  analysis tools

          - ```
            go get -u github.com/uudashr/gopkgs/cmd/gopkgs 
            go get -u github.com/ramya-rao-a/go-outline 
            go get -u github.com/acroca/go-symbols 
            go get -u golang.org/x/tools/cmd/guru 
            go get -u golang.org/x/tools/cmd/gorename 
            go get -u github.com/derekparker/delve/cmd/dlv 
            go get -u github.com/stamblerre/gocode 
            go get -u github.com/rogpeppe/godef 
            go get -u github.com/ianthehat/godef 
            go get -u github.com/sqs/goreturns 
            go get -u golang.org/x/lint/golint
            ```

  - **For Learning go**

    - [tour](https://github.com/golang/tour) - A Tour of Go (introduction to the Go programming language, offline)
      - ```
        go get golang.org/x/tour
        ```
