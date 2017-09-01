Interactif rebase to rewrite commits historic:
----------------------------------------------

 git rebase -i HEAD~10


Cancel last commit:
-------------------

git reset HEAD~


Git lg:
-------

git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
