Vagrant.configure("2") do |config|
  config.vm.box = "centos/7"
  config.vm.provider "virtualbox" do |vb|
  end
  
  #Configura rede em modo bridge
  config.vm.network "public_network", bridge: "1"
  #config.vm.network "public_network", ip: "0.0.0.0"

  #Copia targets com sites a serem monitorados para a maquina virtual
  config.vm.provision "file", source: "targets.yml", destination: "$HOME/targets.yml"
  
  #Chamada para playbook Ansible
  config.vm.provision "ansible" do |ansible|
    ansible.verbose = "v"
    ansible.playbook = "playbook.yaml"
  end
  
end
