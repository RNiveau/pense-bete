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
