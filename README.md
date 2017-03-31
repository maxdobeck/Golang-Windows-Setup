# Golang-Windows-Setup
Quick step guide to getting Go up and running on Windows

# Background
Go or Golang is a staticly typed language that compiles each program to a .exe file.  This executable can be dropped onto any machine and run via the command line, by double clicking it, or as a daemon/process.  Read more at the [FAQ](https://golang.org/doc/faq)

# Setup
Go or Golang has opinions about how to code.  These opinions extend to how your directory is structured.  Go is expecting you to have a Workspace which contains these three directories:
	* src
	* pkg
	* bin
Read more here: [https://golang.org/doc/code.html#Organization]

### Install on Windows

1. Create the directory under your user profile, or another desired location, to hold the `src, bin, and pkg` directores.  This will most likely look like `C:\Users\Your Name\GoWorkspaceDir\`.  Now create the empty directories `src, bin and pkg` inside your `GoWorkspaceDir`.

2. Download and install the windows MSI file from this source:[https://golang.org/dl/]
After installing you can upgrade to a new release by revisiting this page and downloading the next release.  * Check it is installed by running `go version` from Command Prompt or Powershell.

3. Once installation is complete run: `>go env`
You should see output similar to this:
```
set GOARCH=amd64
set GOBIN=C:\Go\bin\
set GOEXE=.exe
set GOHOSTARCH=amd64
set GOHOSTOS=windows
set GOOS=windows
set GOPATH=C:\Users\UserName\GoWorkspace
set GORACE=
set GOROOT=C:\Go
set GOTOOLDIR=C:\Go\pkg\tool\windows_amd64
set GCCGO=gccgo
set CC=gcc
set GOGCCFLAGS=-m64 -mthreads -fmessage-length=0
set CXX=g++
set CGO_ENABLED=1
set PKG_CONFIG=pkg-config
set CGO_CFLAGS=-g -O2
set CGO_CPPFLAGS=
set CGO_CXXFLAGS=-g -O2
set CGO_FFLAGS=-g -O2
set CGO_LDFLAGS=-g -O2
```

4. We'll need to set the key environment variables for go to function on your system.  
	1. Press the Windows key or go to the start menu and search for `system environment`.  
	2. Open the "Edit Environment Variables" control panel and click `Environment Variables` at the bottom of the window.
	3. Focus on the bottom pane and click `New`
	4. Create a new System Variable with the **name** of `GOPATH` and **value** of `C:\Users\Your Username\GoWorkspaceDir` or whatever the path is to the workspace we created in Step One.

5. Test by creating a small Hello World program with these directions: [https://golang.org/doc/install#testing]
6. You should be able to run the program from the command prompt or powershell.