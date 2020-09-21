# History of Deploying Software
In modern history, there are three common ways to deploy software: [[Bare Metal History]], [[Virtual Machine History]], and [[Container History]]

To see the specifics of the different technologies, review the linked pages.

## Comparison
![[Deployment.png]]

To be able to describe deployment, we have an example where we want to deploy the same application twice. The applications use the exact same memory and CPU at all times, but need to have their own copy on disk.

These requirements/restrictions are a bit contrived, but let us make some interesting comparisons.

### CPU
![[CPU.png]]
From the image above, we can see the high level differences between Bare Metal, VM's and Containers. Smaller is better.

In terms of CPU usage, Bare Metal deployments are the obvious winner. They just have less running.

The VM you can see has the worst because it has a hypervisor and two coppies of the OS/Kernel.

*What is a hypervisor?* A [hypervisor][1] is a minimal OS that allows VM's to run as if they were the only thing on the computer.

In the middle are containers. You see there is a small "docker" layer, but it's much smaller than an full OS.

### Memory Usage
![[Memory.png]]

Memory is simmilar to CPU. The Bare Metal host is best, and VM's are the worst.

The VM is worse because it's required to have two coppies of the OS running at any given time.

Docker has some overhead, but not as much as the VM. Something to reconize, there is only one `Docker` layer for both `Application` layers. This means that as the number of applications grow, we don't need to add more. For every VM, the OS overhead is required.

*Note:* We are skipping over some of the finer points of memory usage to make the comparison easier. There are fancy ways to make it better, but those are often proprietary and expensive.

### Disk Usage
![[Disk.png]]

The disk usage is different than CPU and Memory. Docker does better than Bare Metal. This is due to "Layers" where the same file can exist in different docker containers but only physically apear on disk once.

Something else to point out is the OS layer on the diagram for Docker is smaller, this is because much less gets installed onto the host by default and they all live inside the application.

### Security
![[Security.png]]

Security is interesting. Looking at the graph above, the circles are "rings" of protection. Anything inside one ring can effect anything else.

On a Bare Metal host, everything effects everything else. Making security pretty poor.

On VM's each VM is in it's own ring, making it impractical for one VM to effect the other.

With Congainers, each container has it's own ring. If something were able to break out of that ring, they would be able to effect everything else.

This makes VM's much more secure than other technology, and containers better then just Bare Metal deployment.s

[1]: https://en.wikipedia.org/wiki/Hypervisor