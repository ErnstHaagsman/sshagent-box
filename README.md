SSH Agent Test Box
==================

[See the blog post](https://blog.jetbrains.com/pycharm/2017/08/ssh-agent-simplify-ssh-keys/) 
for additional information.

To use
------

First make sure you have the prerequisites installed:

- [Vagrant](https://vagrantup.com)
- Virtualization software: either 
  [Virtualbox](https://www.virtualbox.org/wiki/Downloads), 
  [VMware](https://www.vagrantup.com/vmware/index.html), or 
  [Parallels](http://parallels.github.io/vagrant-parallels/docs/installation/)
  

Then overwrite `files/key.pub` with your own public key (OpenSSH authorized_keys
style)

Finally, run `vagrant up` on the command line in the folder where you
cloned this repository. Alternatively in PyCharm Professional Edition
use Tools | Vagrant | Up.

If you've accidentally brought up the box without first replacing the key, you
can run either `vagrant provision` to insert the new key. Or you can run 
`vagrant destroy -f && vagrant up` to create a new box entirely.