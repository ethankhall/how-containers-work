# What are containers

Containers are composed of two components. The "File System" (aka [image](Image.md)) and "Runtime". The runtime environment is what most people interact with. The runtime portion is where containers really differentiate from VMs. Without the runtime environment, then a container wouldn't be any different than Bare Metal or VMs.

The runtime has two major components: "[Control Groups](Control_Groups.md)" and "[Namespaces](Namespace.md)". With the two of theses together, a container is able to get most of the benefits of VMs with the efficiency of Bare Metal.
