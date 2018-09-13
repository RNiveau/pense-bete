List VM
-------

virsh list

VM details
----------

virsh dumpxml ppr-oro-centreon-2

Increase disk size
------------------

```
virsh shutdown ppr-oro-centreon-2
qemu-img resize /var/lib/libvirt/images/ppr-oro-centreon-2-disk0.img +10G
virsh start ppr-oro-centreon-2
```
Increase cpu
------------

virsh setvcpus <vm_name> <vcpu_count> --config

Increase memory
---------------

virsh setmaxmem <vm_name> <memsize> --config
  
virsh setmem <vm_name> <memsize> --config

Move vm from one host to another
--------------------------------

https://serverfault.com/questions/434064/correct-way-to-move-kvm-vm

Delete vm (don't forget to delete disk after):
----------------------------------------------

force shutdown: virsh destroy host

virsh undefine host
