Launch one shot command:
------------------------

 ansible -i production/ elasticsearch -m shell -a 'sudo apt-get update' --ssh-extra-args '-o StrictHostKeyChecking=no'

Useful ansible.cfg configuration:
---------------------------------

[ssh_connection]
ssh_args=-o ForwardAgent=yes -o ControlMaster=auto -o ControlPersist=60s

End flow:
---------

meta: end_play

