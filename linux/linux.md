Release memory:
---------------
http://wiki.tuxunix.com/index.php/Liberer_de_la_m%C3%A9moire_sous_Linux

List kernel images:
-------------------

dpkg --list | grep linux-image


Kernel messages:
----------------
dmesg --reltime


Tcpdump:
--------
https://openmaniak.com/fr/tcpdump.php

tcpdump  -A -i  eno16777984  -w /tmp/output

Capture only some flags: tcpdump "tcp[tcpflags] & (tcp-syn|tcp-ack) != 0"

Open port:
----------
lsof -i -P | grep -i "listen"

lsof -i  -P -n


Threads number for a pid:
-------------------------
ps -o nlwp 13291


Ssh tunnel:
-----------
ssh -N -L localhost:4242:bc1:4242 rniveau@x.x.x.x


Java cli:
---------
Memory dump: jmap -dump:format=b,file=cheap.bin 60391

Thread dump: jstack 10794 > /tmp/thread-start.tdump

Classloader dump: jmap -clstats 5425


Ps with tree:
-------------

ps axjf

Ps with custom format:
----------------------

ps e -u alksv -o command,vsize,rss,%mem,size

How to know os version on ubuntu:
---------------------------------

lsb_release -a

uname -a

Use fpm to generate package:
----------------------------

fpm  -t deb -s dir -p . --name jenkinspython-api -v 0.3.5  jenkinsapi-0.3.5

Get public key from private ssh key:
------------------------------------

ssh-keygen -y -f ~/.ssh/id_rsa

Generate a ssh key:
-------------------

ssh-keygen -t ed25519 -b 4096


List all networks interfaces:
-----------------------------

ls /sys/class/net/

Flush dns:
----------

rndc flush

Write to haproxy:
-----------------

echo "show info;show stat" | nc -U /var/run/haproxy.sock

Check haproxy configuration:
----------------------------

/usr/sbin/haproxy -c -f /etc/haproxy/haproxy.cfg

Add ip address on interface:
----------------------------

ip address add ip dev ens3

Useful link on tcp parameters:
------------------------------

https://voipmagazine.wordpress.com/tag/tcp_max_syn_backlog/

Find and delete old files:
--------------------------

find /path/to/files* -mtime +5 -exec rm {} \\;

Journalctl:
-----------

journalctl -u nginx.service --since today

ssh-agent:
----------
Launch it: eval \`ssh-agent\`

max process on host:
--------------------

sysctl kernel.pid_max

run  unattended-upgrade manually:
---------------------------------

sudo unattended-upgrade -d

how many processes run:
-----------------------

ps -AL|wc -l

cpu links:
----------

https://www.cyberciti.biz/tips/how-do-i-find-out-linux-cpu-utilization.html

http://www.leonardoborda.com/blog/how-to-configure-sysstatsar-on-ubuntudebian/

ps -eo pcpu,pid,user,args | sort -k 1 -r | head -10

strace -cfp 69607

Files limits:
-------------

ulimit -Sn

1024

ulimit -Hn

1048576

sysctl fs.file-max

fs.file-max = 349217

prlimit --pid 14559

NOFILE     max number of open files                1024      4096
