Setting up git via ssh, follow instructions at the two links
  * https://help.github.com/articles/connecting-to-github-with-ssh/
  * https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/ 

Most important, remember to follow the instruction below if you work from an ssh session at pic 

    Clone with HTTPS, not ssh
    edit .git/config file under your repo directory
    find url=entry under section [remote "origin"]
    change it from url=https://nicola-orlando@github.com/nicola-orlando/lunch_call.git to  url=ssh://git@github.com/nicola-orlando/lunch_call.git. that is, change all the texts before @ symbol to ssh://git
