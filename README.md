# Support with donation
[![Support with donation](http://donation.pcoutinho.com/images/donate-button.png)](http://donation.pcoutinho.com/)

# GoHC

GoHC was made to be a simple continuous integration system made with Go (Golang).

It use a simple plugin mechanism that let you use some different plugins to execute tasks. Today we have two main plugins:  
- CLI = Execute anything from command line  
- JS = Execute a javascript file
  
Some project advantages:
- With javascript you can create scripts that have own logic inside and use bultin function like: http request, regexp, command line execution, json parser and more - dont need use bash script for it
- Everything is a simples JSON file - yes, you dont need one database!
- From project to results - you can versioning everything if you want
- You dont need reload the server for nothing - unless a crash or bug :)
- It use a workspace directory, so you can have a lot of workspaces or one for all projects
- The web interface if nice - made with bootstrap - all results need send HTML
- Each job execution has progress, html ouput compatible with bootstrap, status, etc
- Everything work with API and you can consume using external tools
- It is open-source - you can collaborate
- You can DONATE!

# Configuration

GoHC configuration is a simple INI file called "config.ini".

Example of:

```
[server]
host = :8080
workspaceDir = YOUR-WORKSPACE-DIRECTORY
resourcesDir = YOUR-GOPATH-DIRECTORY + /src/github.com/prsolucoes/gohc
```

# Sample files

I have created a sample project file, a sample config file and a sample javascript file. Check it on **extras/sample** directory.

# Starting

1. Execute: go get -u github.com/prsolucoes/gohc
2. Execute: cd $GOPATH/src/github.com/prsolucoes/gohc
3. Execute: make deps  
4. Execute: make install  
5. Create config file (config.ini) based on some above example  
6. Execute: gohc -f=config.ini
7. Open in your browser: http://localhost:8080  

** dont use character / on any configuration path **

# API

**Check file: controllers/api.go**  
Today we dont have a API doc - but is simple looking code [TODO]  

# Command line interface

You can use some make commands to control GoHC service, like start, stop and update from git repository.

1. make stop   = it will kill current GoHC process
2. make update = it will update code from git and install on $GOPATH/bin directory
3. make deps   = download all dependencies
4. make format = format all files (use it before make a pull-request)

So if you want start your server for example, you only need call "make start".

# Alternative method to Build and Start project

1. go build
2. ./gohc -f=config.ini

# Sugestion

Today, only some functions are implemented. If you need one, you can make a pull-request or send a message in Github Issue.

# Supported By Jetbrains IntelliJ IDEA

![alt text](https://github.com/prsolucoes/gohc/raw/master/extras/jetbrains/logo.png "Supported By Jetbrains IntelliJ IDEA")

# Author WebSite

> http://www.pcoutinho.com

# License

MIT
