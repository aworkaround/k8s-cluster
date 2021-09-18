
Vagrant.configure("2") do |config|
	ssh_pub_key = File.readlines("C:\\Users\\kamal\\.ssh\\id_rsa.pub").first.strip  ## Change the Name with your Username
	## ssh_pub_key = File.readlines("$($HOME)/.ssh/id_rsa.pub").first.strip  ## Use this for Linux
	## Node1
	config.vm.define "node1" do |node1|
		node1.vm.provider "virtualbox" do |vb_node1|
			vb_node1.memory = 2048
			vb_node1.cpus = 2
			vb_node1.name = 'Node1'
			vb_node1.customize ["modifyvm", :id, "--groups", "/Kubernetes Cluster"]
		end
		node1.vm.box = "gusztavvargadr/docker-linux"
		node1.vm.synced_folder "./vagrant_data", "/vagrant_data"
		node1.vm.hostname = "node1"
		node1.vm.network "private_network", ip: "192.168.10.10"
		node1.vm.provision "shell", inline: <<-SHELL
			echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
			echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
			chmod +x /vagrant_data/init.sh && source /vagrant_data/init.sh
		SHELL
	end

	## Node2
	config.vm.define "node2" do |node2|
		node2.vm.provider "virtualbox" do |vb_node2|
			vb_node2.memory = 2048
			vb_node2.cpus = 2
			vb_node2.name = 'Node2'
			vb_node2.customize ["modifyvm", :id, "--groups", "/Kubernetes Cluster"]
		end
		node2.vm.box = "gusztavvargadr/docker-linux"
		node2.vm.synced_folder "./vagrant_data", "/vagrant_data"
		node2.vm.hostname = "node2"
		node2.vm.network "private_network", ip: "192.168.10.11"
		node2.vm.provision "shell", inline: <<-SHELL
			echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
			echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
			chmod +x /vagrant_data/init.sh && source /vagrant_data/init.sh
		SHELL
	end

	## Node3
	config.vm.define "node3" do |node3|
		node3.vm.provider "virtualbox" do |vb_node3|
			vb_node3.memory = 2048
			vb_node3.cpus = 2
			vb_node3.name = 'Node3'
			vb_node3.customize ["modifyvm", :id, "--groups", "/Kubernetes Cluster"]
		end
		node3.vm.box = "gusztavvargadr/docker-linux"
		node3.vm.synced_folder "./vagrant_data", "/vagrant_data"
		node3.vm.hostname = "node3"
		node3.vm.network "private_network", ip: "192.168.10.12"
		node3.vm.provision "shell", inline: <<-SHELL
			echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
			echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
			chmod +x /vagrant_data/init.sh && source /vagrant_data/init.sh
		SHELL
	end
end
