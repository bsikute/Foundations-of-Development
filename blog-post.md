## Virtualization vs. Containerization
Virtualization enables workloads to run in environments that are separated from their underlying hardware by a layer of abstraction. This abstraction allows servers to be broken up into VMs that can run different operating systems. Thus a virtual machine (VM) is an emulation of particular computer system, its resources such as CPU, RAM and DISK space using a piece of computer software called a hypervisor that creates and runs virtual machines. 
To better understand this concept, there is that has one giant room for one guest. Nobody needs that much space, so 90% of the building goes unused.
Container technology offers an alternative method for virtualization, in which a single operating system on a host can run many different applications. Containers provide isolated runtime environments for applications: the entire user space environment is exclusively presented to the container, and any changes to it do not impact other containers’ environments. 
One way to think of containers vs. VMs is that while VMs run several different operating systems on one compute node, container technology offers the opportunity to virtualize the operating system itself.

![Comparison](https://i2.wp.com/www.docker.com/blog/wp-content/uploads/Blog.-Are-containers-..VM-Image-1-1024x435.png?ssl=1)
Fig .1: Comparison of how containers and virtual machines are organized. Source: Docker

### Which one is better?
|Parameter	|Virtualization|Containerization|
| ---------|------------|-----------------|
|Guest OS|	Each VM runs on a hypervisor and Kernel is loaded into its own memory region	|All the guests share same OS and Kernel. kernel image is loaded into the physical memory|
|Networking|	Can be linked to virtual or physical switches.| Hypervisors have the buffers for IO performance improvement, NIC bonding, etc.	Leveraged standard IPC mechanisms like signals, pipes, sockets, etc. Advanced features like NIC bonding still not available|
|Security	|Complete Isolation|	Isolation using technology like namespaces|
|Performance|	Suffer from a small overhead as the Machine instructions are translated from Guest to Host OS	|Provide near native performance as compared to the underlying Host OS|
|Isolation|	Higher level of isolation - Need special techniques for file sharing	|Subdirectories can be mounted transparently and can be shared|
|Startup time|	VM takes a few minutes to boot up	|Containers can be booted up in a few seconds|
|Storage|	VMs take much more storage as the whole OS kernel and its associated programs have to be installed and run|	Containers take lower amount of storage as the base OS is shared|

If you just want to have a number of separate instances to run applications, a container environment often provides greater efficiency, both in managing the application environment, starting the application instances, and in resource consumption. Simple modification and deployment of application environments has been a design principle of container solutions like Docker. 
If you want to have best isolation of environments and come from a server virtualization perspective, then system virtualization may be more relevant: Noisy neighbours are much less of an issue than with containers. While isolation in containers is still improving, virtual machine isolation is still superior. 

