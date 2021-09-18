## How to create Docker Swarm cluster using vagrant

- Download & install Vagrant from Vagrant's official website.
- Download & install VirtualBox from it's official website.
- Clone this repository and open this repository in CMD/PowerShell/Terminal.
- Run command `vagrant up`. It will take a sevral minutes, in my case took 10 minutes.
- Done :)

## Useful commands

- To shut-down this cluster gracefully, use `vagrant halt` command.
- To apply new changes you might have made on Vagrantfile, use `vagrant reload`.
- To start the halted/shut-down state cluser, use `vagrant up --no-provision`.
- To finally destory all the virtual machines, use `vagrant destroy`.
- These commands will only work from docker-box directory.

## How to SSH

One way is to `vagrant ssh node1` to ssh into node1.
Other way is to use command as below ->
- For NODE1 -> `ssh -i .vagrant\machines\node1\virtualbox\private_key vagrant@10.0.0.10`
- For NODE1 -> `ssh -i .vagrant\machines\node2\virtualbox\private_key vagrant@10.0.0.11`
- For NODE1 -> `ssh -i .vagrant\machines\node3\virtualbox\private_key vagrant@10.0.0.12`

You can create alias of these commands for simplicity. For example, `alias ssh-node1='ssh -i .vagrant\machines\node1\virtualbox\private_key vagrant@10.0.0.10'`