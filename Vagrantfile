
Vagrant.configure("2") do |config|
  ssh_pub_key = File.readlines("/home/kamal/.ssh/id_rsa.pub").first.strip
  ## Node1
  config.vm.define "node1" do |node1|
    node1.vm.provider "virtualbox" do |vb_node1|
      vb_node1.memory = 2048
      vb_node1.cpus = 2
    end
    node1.vm.box = "gusztavvargadr/docker-linux"
    config.vm.synced_folder "./vagrant_data", "/vagrant_data"
    node1.vm.hostname = "node1"
    node1.vm.network "private_network", ip: "192.168.10.10"
    node1.vm.provision "shell", inline: <<-SHELL
      apt-get update && apt-get upgrade -y
      echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
      echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
      hostnamectl set-hostname node1
      swapoff -a
      apt-get update && apt-get install -y apt-transport-https curl
      curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
      cat <<EOF >/etc/apt/sources.list.d/kubernetes.list
deb http://apt.kubernetes.io/ kubernetes-xenial main
EOF
      apt-get update
      apt-get install -y kubelet kubeadm kubectl
    SHELL
  end
  ## Node2
  config.vm.define "node2" do |node2|
    node2.vm.provider "virtualbox" do |vb_node2|
      vb_node2.memory = 2048
      vb_node2.cpus = 2
    end
    node2.vm.box = "gusztavvargadr/docker-linux"
    config.vm.synced_folder "./vagrant_data", "/vagrant_data"
    node2.vm.hostname = "node2"
    node2.vm.network "private_network", ip: "192.168.10.11"
    node2.vm.provision "shell", inline: <<-SHELL
      apt-get update && apt-get upgrade -y
      echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
      echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
      hostnamectl set-hostname node2
      swapoff -a
      apt-get update && apt-get install -y apt-transport-https curl
      curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
      cat <<EOF >/etc/apt/sources.list.d/kubernetes.list
deb http://apt.kubernetes.io/ kubernetes-xenial main
EOF
      apt-get update
      apt-get install -y kubelet kubeadm kubectl
    SHELL
  end
  ## Node3
  config.vm.define "node3" do |node3|
    node3.vm.provider "virtualbox" do |vb_node3|
      vb_node3.memory = 2048
      vb_node3.cpus = 2
    end
    node3.vm.box = "gusztavvargadr/docker-linux"
    config.vm.synced_folder "./vagrant_data", "/vagrant_data"
    node3.vm.hostname = "node3"
    node3.vm.network "private_network", ip: "192.168.10.12"
    node3.vm.provision "shell", inline: <<-SHELL
      apt-get update && apt-get upgrade -y
      echo #{ssh_pub_key} >> /home/vagrant/.ssh/authorized_keys
      echo #{ssh_pub_key} >> /root/.ssh/authorized_keys
      hostnamectl set-hostname node3
      swapoff -a
      apt-get update && apt-get install -y apt-transport-https curl
      curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
      cat <<EOF >/etc/apt/sources.list.d/kubernetes.list
deb http://apt.kubernetes.io/ kubernetes-xenial main
EOF
      apt-get update
      apt-get install -y kubelet kubeadm kubectl
    SHELL
  end
end
