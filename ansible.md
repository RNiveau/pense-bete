Launch one shot command:
------------------------

 ansible -i production/ elasticsearch -m shell -a 'sudo apt-get update' --ssh-extra-args '-o StrictHostKeyChecking=no'
