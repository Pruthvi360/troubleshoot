# GNS VM in Proxmox Error
# KVM support = False

If your Proxmox hypervisor is Intel CPU, run the following command to check if nested virtualization is enabled in it.
```
cat /sys/module/kvm_intel/parameters/nested
```
It should be Y

debian desktop > should not get any output
```
egrep --color -i "svm|vmx" /proc/cpuinfo
```

```
qm set 105 --cpu host
```
# set the CPU to "host"
