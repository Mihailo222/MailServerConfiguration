VAGRANTFILE_API_VERSION = "2"
Vagrant.configure(VAGRANTFILE_API_VERSION) do |config|

#    config.vm.provision "ansible" do |ansible|
#      ansible.playbook = "playbook.yml"
#      ansible.compatibility_mode = "2.0"
#    end

    config.vm.define "dns" do |dns|
        dns.vm.box = "geerlingguy/ubuntu2004"
        dns.ssh.insert_key = false
        dns.vm.hostname = "dns"
        dns.vm.network "private_network", ip: "192.168.56.10", netmask: "255.255.255.0"
  
 
        dns.vm.provision "ansible" do |ansible|
        ansible.playbook = "dns.yml"
        end
  
    end




    config.vm.define "mailserver" do |mail|
        mail.vm.box = "geerlingguy/ubuntu2004"
        mail.ssh.insert_key = false
        mail.vm.hostname = "mail1.domain1.com"
        mail.vm.network "private_network", ip: "192.168.56.11", netmask: "255.255.255.0"


        mail.vm.provision "ansible" do |ansible|
        ansible.playbook = "mail.yml"
        end

    end
  

end
