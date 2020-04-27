
Active hidden file:
-------------------

defaults write com.apple.finder AppleShowAllFiles YES

killall Finder


Change screenshot location:
---------------------------

defaults write com.apple.screencapture location /path/

killall SystemUIServer


Install bash 4:
---------------

http://clubmate.fi/upgrade-to-bash-4-in-mac-os-x/

Install GNU commands:
---------------------

brew install coreutils findutils gnu-tar gnu-sed gawk gnutls gnu-indent gnu-getopt

Flush dns:
----------

sudo killall -HUP mDNSResponder;sudo killall mDNSResponderHelper;sudo dscacheutil -flushcache

Show route table:
-----------------

netstat -nr

Add route:
----------

sudo route add -net 172.32.16.0/20 172.30.3.250

Find which programme listen port:
---------------------------------

lsof -NP -i:8080

Set password to zip:
--------------------

zip -er zip-name dir
