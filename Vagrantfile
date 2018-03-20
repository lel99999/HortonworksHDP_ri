Vagrant.configure("2") do |config|
  
  config.vm.provider "virtualbox" do |v|
    v.memory = "1024"
    v.cpus = 2
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
  end
  config.vm.define "winAD01" do |winAD01|
    winAD01.vm.box = "mwrock/Windows2012R2"
    winAD01.vm.hostname = "winAD01.hdpdev.com"
    winAD01.vm.network "private_network", ip: "192.168.60.151"
  end
  config.vm.define "hdptest" do |hdptest|
    hdptest.vm.box = "bento/centos-6.7"
    hdptest.vm.hostname = "hdptest"
    #hdptest.vm.box = "wharton-wcit/centos6py36"
    hdptest.vm.network "private_network", ip: "192.168.60.162"
  end
# config.vm.define "hdprepo" do |hdprepo|
#   hdprepo.vm.box = "bento/centos-6.7"
#   hdprepo.vm.hostname = "hdprepo"
#   #hdprepo.vm.box = "wharton-wcit/centos6py36"
#   hdprepo.vm.network "private_network", ip: "192.168.60.159"
# end
  config.vm.define "ambari" do |ambari|
    ambari.vm.box = "bento/centos-6.7"
    ambari.vm.hostname = "ambari.hdpdev.com"
    ambari.vm.network "private_network", ip: "192.168.60.159"
#   ambari.vm.provision "file",source:"~/Downloads/jdk-8u151-linux-x64.tar.gz",destination: "/opt"
#   ambari.vm.provision "shell", :inline => "sudo wget http://public-repo-1.hortonworks.com/ambari/centos6/2.x/updates/2.6.0.0/ambari.repo -O /etc/yum.repos.d/ambari.repo"
    ambari.vm.provision "shell", :inline => "sudo wget http://public-repo-1.hortonworks.com/ambari/centos6/2.x/updates/2.6.1.5/ambari.repo -O /etc/yum.repos.d/ambari.repo"
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari.hdpdev.com ambari' >> /etc/hosts"
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01.hdpdev.com nn01' >> /etc/hosts"
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01.hdpdev.com snn01' >> /etc/hosts"
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01.hdpdev.com dn01' >> /etc/hosts"
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02.hdpdev.com dn02' >> /etc/hosts"
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03.hdpdev.com dn03' >> /etc/hosts"

    ambari.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_ambari.yml"
    end
  end
  config.vm.define "mit01" do |mit01|
    mit01.vm.box = "bento/centos-6.7"
    mit01.vm.hostname = "mit01.hdpdev.com"
    mit01.vm.network "private_network", ip: "192.168.60.152"
    mit01.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari.hdpdev.com ambari' >> /etc/hosts"
    mit01.vm.provision "shell", :inline => "sudo echo '192.168.60.152 mit01.hdpdev.com mit01' >> /etc/hosts"
    mit01.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_mitkerberos.yml"
    end
  end
end

Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
#   v.memory = "2048"
    v.memory = "1536"
    v.cpus = 2
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
  end
  config.vm.define "nn01" do |nn01|
  #config.vm.define "mstr01" do |mstr01|
    #nn01.customize ["modifyvm", :id, "--memory", 2048]
    nn01.vm.box = "bento/centos-6.7"
    nn01.vm.hostname = "nn01.hdpdev.com"
    #mstr01.vm.hostname = "mstr01"
    nn01.vm.network "private_network", ip: "192.168.60.160"
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari.hdpdev.com ambari' >> /etc/hosts"
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01.hdpdev.com nn01' >> /etc/hosts"
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01.hdpdev.com snn01' >> /etc/hosts"
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01.hdpdev.com dn01' >> /etc/hosts"
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02.hdpdev.com dn02' >> /etc/hosts"
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03.hdpdev.com dn03' >> /etc/hosts"
    nn01.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_allnodes.yml"
    end
  end
  config.vm.define "snn01" do |snn01|
  #config.vm.define "mstr01" do |mstr01|
    #snn01.customize ["modifyvm", :id, "--memory", 2048]
    snn01.vm.box = "bento/centos-6.7"
    snn01.vm.hostname = "snn01.hdpdev.com"
    snn01.vm.network "private_network", ip: "192.168.60.161"
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari.hdpdev.com ambari' >> /etc/hosts"
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01.hdpdev.com nn01' >> /etc/hosts"
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01.hdpdev.com snn01' >> /etc/hosts"
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01.hdpdev.com dn01' >> /etc/hosts"
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02.hdpdev.com dn02' >> /etc/hosts"
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03.hdpdev.com dn03' >> /etc/hosts"
    snn01.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_allnodes.yml"
    end
  end
  config.vm.define "dn01" do |dn01|
    #dn01.customize ["modifyvm", :id, "--memory", 2048]
    dn01.vm.box = "bento/centos-6.7"
    dn01.vm.hostname = "dn01.hdpdev.com"
    dn01.vm.network "private_network", ip: "192.168.60.165"
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari.hdpdev.com ambari' >> /etc/hosts"
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01.hdpdev.com nn01' >> /etc/hosts"
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01.hdpdev.com snn01' >> /etc/hosts"
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01.hdpdev.com dn01' >> /etc/hosts"
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02.hdpdev.com dn02' >> /etc/hosts"
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03.hdpdev.com dn03' >> /etc/hosts"
    dn01.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_allnodes.yml"
    end
  end
  config.vm.define "dn02" do |dn02|
    #dn02.customize ["modifyvm", :id, "--memory", 2048]
    dn02.vm.box = "bento/centos-6.7"
    dn02.vm.hostname = "dn02.hdpdev.com"
    dn02.vm.network "private_network", ip: "192.168.60.166"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari.hdpdev.com ambari' >> /etc/hosts"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01.hdpdev.com nn01' >> /etc/hosts"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01.hdpdev.com snn01' >> /etc/hosts"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01.hdpdev.com dn01' >> /etc/hosts"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02.hdpdev.com dn02' >> /etc/hosts"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03.hdpdev.com dn03' >> /etc/hosts"
    dn02.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_allnodes.yml"
    end
  end
  config.vm.define "dn03" do |dn03|
    dn03.vm.box = "bento/centos-6.7"
    dn03.vm.hostname = "dn03.hdpdev.com"
    dn03.vm.network "private_network", ip: "192.168.60.167"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari.hdpdev.com ambari' >> /etc/hosts"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01.hdpdev.com nn01' >> /etc/hosts"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01.hdpdev.com snn01' >> /etc/hosts"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01.hdpdev.com dn01' >> /etc/hosts"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02.hdpdev.com dn02' >> /etc/hosts"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03.hdpdev.com dn03' >> /etc/hosts"
    dn03.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_allnodes.yml"
    end
  end
# Vagrant.configure("2") do |config|
#   config.vm.provider "virtualbox" do |v|
#     v.memory = "1024"
#     v.cpus = 1
#     v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
#   end

# end
  #config.vm.provision "ansible" do |ansible|
  #  ansible.playbook = "hdp_singlesetup.yml"
  #  ansible.inventory_path = "vagrant_hosts"
  #end
  #config.vm.provision "ansible" do |ansible|
    #ansible.playbook = "hdp_singlesetup.yml"
    #ansible.inventory_path = "vagrant_hosts"
    #ansible.tags = ansible_tags
    #ansible.extra_vars = ansible_extra_vars
    #ansible.limit = ansible_limit
  #end

end
