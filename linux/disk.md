How to know filesystem of disk:
-------------------------------
fsck -N /dev/sda

How to know mapping between disk and partitions:
------------------------------------------------
lsblk

another usefull tools: http://www.binarytides.com/linux-command-check-disk-partitions/

How to find partition id:
-------------------------

blkid /dev/sdc1


Operation about logical group and lvm:
--------------------------------------
vgdisplay

vgscan

create lvm http://www.thegeekstuff.com/2010/08/how-to-create-lvm


Formating partition:
--------------------
mkfs.ext4 /dev/sdb1

Check health disk:
------------------
 smartctl -t short|long /dev/sdb

Get disk uuid:
--------------
ls -l /dev/disk/by-uuid

Raid setup:
-----------

https://raid.wiki.kernel.org/index.php/RAID_setup
