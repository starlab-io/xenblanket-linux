# Linux Kernel 4.15.5 for Xen Blanket 4.12

This repository contains the Linux kernel patch to add Xen Blanket support to the Linux Kernel version 4.15.5.

The resulting kernel is compatible with the XenBlanket-enabled Xen 4.12 or pre-Xen-4.13 staging branch hypervisor.

The Linux kernel that this produces is for use as a nested dom0 kernel.

````
# Obtain the vanilla kernel source
wget https://cdn.kernel.org/pub/linux/kernel/v4.x/linux-4.15.5.tar.xz

# Unpack
xz -d --stdout linux-4.15.5.tar.xz | tar xf -

# Apply the patch
patch -p1 <xenblanket-linux-4.15.5.patch
````

Now build the kernel as per usual procedure. A sample kernel config is included within the patch.

To boot the kernel, you will need the XenBlanket-enabled Xen hypervisor.