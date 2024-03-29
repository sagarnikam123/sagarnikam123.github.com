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
            go install -v github.com/ramya-rao-a/go-outline@latest
            go install -v golang.org/x/tools/gopls@latest
            go install -v github.com/go-delve/delve/cmd/dlv@latest
            go install -v honnef.co/go/tools/cmd/staticcheck@latest
            go install -v github.com/cweill/gotests@latest
            ```
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

    - [tour](https://go.dev/tour/welcome/3) - A Tour of Go (introduction to the Go programming language, offline)
      - This will place a tour binary in your GOPATH's bin directory
      - ```
        go install golang.org/x/website/tour@latest

        # run it
        $HOME/go/bin/tour
        ```
