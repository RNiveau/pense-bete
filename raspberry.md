Format sd card:
---------------

sudo dd bs=64m if=/Users/Xebia/Downloads/2018-11-13-raspbian-stretch.img of=/dev/rdisk2

Allow ssh:
----------

touch /boot/ssh

Take a picture:
---------------

raspistill -o image.jpg
