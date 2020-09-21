# Virtual Machines
Virtual Machines are a way to run multiple comptuers on one physical machine.

The physical machine usually runs a paired down OS called a hypervisor. The hypervisor is responsible for:
- Sharing CPU resources across the VMs.
- Giving RAM to the VMs.
- Emulating Disk and Network devices to expose the the VM's.

By itself, a hypervisor isn't intended to run much software. The deployment is usually very small and has a limited set of functionality.

The hypervisor can:
- Store disk Images to start VM's based on an existing image.
- Stop/pause/move an existing VM to another hypervisor.
- Attach remote storage as if it were local for VMs.

*Note:* In general there are two ways to treat a VM, as a "pet" or as "cattle"; Ref: [Cattle vs Pets][1]. From here on we'll treat VM's at "cattle".

When deploying another machine into the fleet, only a few parameters need to be provides; like CPU, RAM and what disk to start with.

In advanced setups, the CI system will "bake" images. This makes deploying software much simpler, because the hypervisor only needs to start a VM using the provided disk without any other management/setup required. Every version of software creates a new image. Adding second copy of the software means starting a new VM with the same base image. This concept is called "[immutable infrastructure][2]"

### Advantages
- Easier to deploy new software with baked images.
- Isolation between the different VM's.
- From the OS, looks like a bare metal deployement.
- Easy to migrate from bare metal to VM's.

### Disadvantages
- Each application has a full copy of the OS and kernel.
- Sharing resources (memory & CPU) is more complicated than bare metal.
- There is much more "hardware" waist with this overhead.

### Security
Hypervisors create a new security ring (-1) they use to isolate other VMs from eachother.

The hypervisor is able to isolate the VM's from each other. This makes the security 
better than bare metal.
[1]: https://medium.com/@Joachim8675309/devops-concepts-pets-vs-cattle-2380b5aab313
[2]: https://www.digitalocean.com/community/tutorials/what-is-immutable-infrastructure