## Error: Kernel header not found for the kernel4.18.0

Open devices and click on **"Insert guest addtions CD image"**

## If error still persist

yum install kernel-devel

## update the kernel

yum update kernel kernel-headers
reboot now

## install gcc

yum install gcc

## cd /run/media/pruthvi/VBox_GAs_7.0.6

./VBoxLinuxAddtion.run

