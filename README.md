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

The hypervisor patch series for Xen has been posted to the `xen-devel` mailing list:

`[RFC 0/9] The Xen Blanket: hypervisor interface for PV drivers on nested Xen`

https://lists.xenproject.org/archives/html/xen-devel/2019-06/msg01359.html

`[RFC 1/9] x86/guest: code movement to separate Xen detection from guest functions`

https://lists.xenproject.org/archives/html/xen-devel/2019-06/msg01358.html

`[RFC 2/9] x86: Introduce Xen detection as separate logic from Xen Guest support.`

https://lists.xenproject.org/archives/html/xen-devel/2019-06/msg01360.html

`[RFC 3/9] x86/nested: add nested_xen_version hypercall`

https://lists.xenproject.org/archives/html/xen-devel/2019-06/msg01361.html

`[RFC 4/9] XSM: Add hook for nested xen version op; revises non-nested version op`

https://lists.xenproject.org/archives/html/xen-devel/2019-06/msg01362.html

`[RFC 5/9] x86/nested, xsm: add nested_memory_op hypercall`

https://lists.xenproject.org/archives/html/xen-devel/2019-06/msg01363.html

`[RFC 6/9] x86/nested, xsm: add nested_hvm_op hypercall`

https://lists.xenproject.org/archives/html/xen-devel/2019-06/msg01364.html

`[RFC 7/9] x86/nested, xsm: add nested_grant_table_op hypercall`

https://lists.xenproject.org/archives/html/xen-devel/2019-06/msg01365.html

`[RFC 8/9] x86/nested, xsm: add nested_event_channel_op hypercall`

https://lists.xenproject.org/archives/html/xen-devel/2019-06/msg01366.html

`[RFC 9/9] x86/nested, xsm: add nested_schedop shutdown hypercall`

https://lists.xenproject.org/archives/html/xen-devel/2019-06/msg01367.html
