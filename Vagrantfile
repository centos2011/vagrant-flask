Vagrant.configure("2") do |config|
 
 config.vm.box      = "ubuntu/trusty64"
 config.vm.hostname = "web-server"
 config.vm.network "private_network", ip: "10.10.10.20"

 config.vm.provider :virtualbox do |vb|
   vb.customize ["modifyvm", :id, "--cpuexecutioncap", "100"]
   vb.name = "server"
 end

 #Run Ansible from the Vagrant Host
 config.vm.provision "ansible" do |ansible|
   ansible.limit               = "all,localhost" 
   ansible.playbook            = "playbook.yml"
   ansible.compatibility_mode  = "2.0"
 end 

end

