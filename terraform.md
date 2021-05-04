Workspace stuff:
----------------

terraform workspace show

terraform workspace list

terraform workspace select prd

Get output:
-----------

 terraform output --module aks-cluster kube_config

Forget resources:
-----------------

terraform state rm resources

Format files:
-------------

terraform fmt -recursive -diff

Provider lock on linux and mac:
-------------------------------

terraform providers lock -platform=darwin_amd64  -platform=linux_amd64
