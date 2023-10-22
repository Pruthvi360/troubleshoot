# Importing VM from VirtualBox to Proxmox
# Step-1: Open Virtual Box> Right click on VM> Select Export to OCI>**Format: Open Virtualization Format 0.9**> Rest Leave it Default.

# Step-2: Open Proxmox create VM
```
General: Provide Name
OS: Do not use any media
System: Select Qemu Agent
Disk: Leave Default
CPU: 4 cores, Type: x86-64-v2-AES
Enable NUMA: Select
Memory: 4096, Min Memory: 256, Ballooning: Select
Network: Leave Default
Confirm: Click Finish
```
# Step-3: Select Hard-disk and detach > remove

# Step-4: Copy file from window machine to proxmox shell
```
scp C:\Users\HP\Documents\netbox.ova root:192.168.0.100:/home
```
# Step-5: Login to proxmox shell, Extract create qcow2 -format and attach to the VM
```
tar -xvf netbox.ova
qm importdisk <VM-ID> netbox.vmdk <storage volume of proxmox> -format qcow2
```
# Step-6: back to proxmox
```
Select VM> Hardware> Unused disk> edit> add> Select options> Click boot order> Drag hard disk to 2nd order> Start the VM
```
