# roger-skyline-1
A Hive Helsinki project about installing a virtual machine and the basics of system and network administration.

## Setting up the Virtual Machine

We need a VM with a disk size of 8GB, that has at least one 4.2GB partition.
I set up the VM on VirtualBox with Linux OS, Debian 64-bit with a harddisk size of 8GB.
The `partition method` needs to be set up as `manual` to create the 4.2GB partition.

## Network and Security

__Tasks:__
- Create a non-root user to connect to the machine and work
- Use __sudo__ to be able to perform special rights operations
- Configure it to have a static __IP__ and a __Netmask__ in \30 (we dont want to use DHCP service)
- *SSH* access has to be done with __publickeys__
- Set rules of __firewall__ only with services used outside of VM
- You have to set a __DOS (Denial of Service Attack)__ protection on your open ports of your VM
- Set protection against scans on your VM’s open ports
- Stop services you dont need for this project
- Create __script__ that updates all the sources of package (scheduled task for this script once a week at 4AM and every time the machine reboots)
- Make a script to monitor changes of the /etc/__crontab__ file and sends an email to root if it has been modified (create a scheduled script task every day at midnight)

----
# 1.
When setting up the machine I created a non-root user. To access sudo with the non-root user we first
need to install the `sudo` command. For this we need to switch to the root by the `su` command.

Then we can install sudo with the command:
```
$ apt-get install sudo vim -y
```
Tog give the non-root user sudo rights we need to add the user to the `/etc/sudoers` file.
`username ALL=(ALL:ALL)` should be added to the *# User priviliege specification* -section.

---
# 2.


