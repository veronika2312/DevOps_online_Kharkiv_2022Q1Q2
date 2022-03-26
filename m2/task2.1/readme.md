2.1

VM connections check

| Mode | VM&gt;Host | VM&lt;Host | VM1&lt;&gt;VM2 | VM&gt;Net/LAN | VM&lt;Net/LAN |
| --- | --- | --- | --- | --- | --- |
| Host-only | + | + | + | - | - |
| Internal | - | + | + | - | - |
| Bridged | + | + | + | + | + |
| NAT | + | + | - | + | - |
| NAT network | + | + | + | + | - |

1.What are the most popular hypervisors for infrastructure virtualization?

As far as I know and according to the resent overviews, the most used and convenient hypervisors are Hyper-V, VMware vSphere Hypervisor, Azure Virtual Machines, Oracle VM. It is worth mentioning that the Server Virtualization product must allow users to partition physical servers into multiple virtual instances, enable easy management of scalable virtual environments and offer access to a built-in or third-party control panel through which virtual servers can be managed.

2.Briefly describe the main differences of the most popular hypervisors.

Type 1 hypervisors are Citrix/Xen Server, VMware ESXi and Microsoft Hyper-V (also referred to as the &quot;bare-metal&quot; hypervisors) run directly on the physical hardware of the host machine and don&#39;t have to load an underlying Operating System before that.

Type 2 hypervisors are installed on an existing OS what makes it a hosted hypervisor. Examples of type 2 Hypervisors include Microsoft Virtual PC, Oracle Virtual Box, VMware Workstation, Oracle Solaris Zones, VMware Fusion, Oracle VM Server for x86 and more.

Type 1 hypervisors are used in production and the low cost_ _and ease of installation of a Type 2 hypervisor make it an ideal option for home labs or other test environments.

![VM screenshot](screenshot.png)

Logs for VM tasks can be found [here](https://github.com/veronika2312/DevOps_online_Kharkiv_2022Q1Q2/blob/main/m2/task2.1/DESKTOP-9M8QVPI_Krasilia_VM1/Logs)