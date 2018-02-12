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
