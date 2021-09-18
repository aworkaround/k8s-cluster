## How to create Kubernetes cluster using vagrant.

- Download & install Vagrant from Vagrant's official website.
- Download & install VirtualBox from it's official website.
- Clone this repository and open this repository in CMD/PowerShell/Terminal.
- Go to Vagrantfile and change the LINE-3 path with your own user path.
- Run command `vagrant up`. It will take a sevral minutes, in my case took 10 minutes.
- You need to use `kubeadm init` in Master node (node1) and then join from other Nodes.
- Done :)

## Useful commands

- To shut-down this cluster gracefully, use `vagrant halt` command.
- To apply new changes you might have made on Vagrantfile, use `vagrant reload`.
- To start the halted/shut-down state cluser, use `vagrant up --no-provision`.
- To finally destory all the virtual machines, use `vagrant destroy`.
- These commands will only work from docker-box directory.

## How to SSH

One way is to `vagrant ssh node1` to ssh into node1. Similarly for node2 and node3.

Other way is to use command as below ->

- For NODE1 -> `ssh -i .vagrant\machines\node1\virtualbox\private_key vagrant@192.168.10.10`
- For NODE1 -> `ssh -i .vagrant\machines\node2\virtualbox\private_key vagrant@192.168.10.11`
- For NODE1 -> `ssh -i .vagrant\machines\node3\virtualbox\private_key vagrant@192.168.10.12`

OR (If you're running Vagrant file without any change. Below commands should also work)

- For NODE1 -> `ssh vagrant@192.168.10.10`
- For NODE1 -> `ssh vagrant@192.168.10.11`
- For NODE1 -> `ssh vagrant@192.168.10.12`

You can create alias of these commands for simplicity. For example, `alias ssh-node1='ssh -i .vagrant\machines\node1\virtualbox\private_key vagrant@10.0.0.10'`