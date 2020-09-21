# Containers
Containers are a conglomeration of Linux technologies that try to take the best of both Bare Metal and VM's.

## VM vs Bare Metal
### Kernel Overhead
Each VM is an isolated from eachother. This means that each VM has it's own kernel, which means everything inside the kernel is duplicated.
### Startup TIme
On a Bare Metal machine, you just starte a process. To deploy a new app inside a VM you have to start the VM, then start the application making startup much longer.
### Security Isolation
Each VM is isolated from eachother, that makes VM's more secure with all things being the same than Bare Metal.
### Unique Resources
Inside any machine, only one process can bind to `0.0.0.0:1234`. Each VM has it's own IP address, there for the process can start twice on `1234`, but with different IP's. On Bare Metal you cannot use the same port twice.

## What Do Containers Do?
- Each container runs on the host Kernel.
	- startup faster
	- less secure
- Unique Resources
	- Each container gets it's own IP, which means that applications inside containers can bind to the same port successfully.