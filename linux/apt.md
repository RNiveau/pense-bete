Apt commands:
-------------
Get version available in repo: apt-cache madison jenkins

Get version installed in host: dpkg -s haproxy

List files from package: dpkg -c /home/rniveau/oracle-jdk_1.8.0.144_amd64.deb

sudo apt-get update        # Fetches the list of available updates

sudo apt-get upgrade       # Strictly upgrades the current packages

sudo apt-get dist-upgrade  # Installs updates (new ones)

where is install my package: dpkg -L oracle-jdk
