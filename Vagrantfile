Vagrant.configure("2") do |config|
  
  config.vm.provider "virtualbox" do |v|
    v.memory = "1024"
    v.cpus = 2
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
  end
  config.vm.define "winAD01" do |winAD01|
    winAD01.vm.box = "mwrock/Windows2012R2"
    winAD01.vm.hostname = "winAD01"
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
  #config.vm.define "mstr01" do |mstr01|
    #nn01.customize ["modifyvm", :id, "--memory", 2048]
    ambari.vm.box = "bento/centos-6.7"
    ambari.vm.hostname = "ambari"
    #mstr01.vm.hostname = "mstr01"
    #mtrr01.vm.box = "wharton-wcit/centos6py36"
    ambari.vm.network "private_network", ip: "192.168.60.159"
    ambari.vm.provision "file",source:"~/Downloads/jdk-8u151-linux-x64.tar.gz",destination: "/opt"
    ambari.vm.provision "shell", :inline => "sudo wget http://public-repo-1.hortonworks.com/ambari/centos6/2.x/updates/2.6.0.0/ambari.repo -O /etc/yum.repos.d/amari.repo"
#   ambari.vm.provision :shell,
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari ambari.local' >> /etc/hosts"
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01 nn01.local' >> /etc/hosts"
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01 snn01.local' >> /etc/hosts"
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01 dn01.local' >> /etc/hosts"
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02 dn02.local' >> /etc/hosts"
    ambari.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03 dn03.local' >> /etc/hosts"

    ambari.vm.provision "ansible" do |ansible|
      ansible.playbook = "deploy_ambari.yml"
    end
  end
end

Vagrant.configure("2") do |config|
  config.vm.provider "virtualbox" do |v|
    v.memory = "2048"
    v.cpus = 2
    v.customize ["modifyvm", :id, "--cpuexecutioncap", "70"]
  end
  config.vm.define "nn01" do |nn01|
  #config.vm.define "mstr01" do |mstr01|
    #nn01.customize ["modifyvm", :id, "--memory", 2048]
    nn01.vm.box = "bento/centos-6.7"
    nn01.vm.hostname = "nn01"
    #mstr01.vm.hostname = "mstr01"
    #mtrr01.vm.box = "wharton-wcit/centos6py36"
    nn01.vm.network "private_network", ip: "192.168.60.160"
#    nn01.vm.provision :shell,
#   nn01.vm.provision "shell" do |s|
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari ambari.local' >> /etc/hosts"
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01 nn01.local' >> /etc/hosts"
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01 snn01.local' >> /etc/hosts"
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01 dn01.local' >> /etc/hosts"
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02 dn02.local' >> /etc/hosts"
    nn01.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03 dn03.local' >> /etc/hosts"
  end
  config.vm.define "snn01" do |snn01|
  #config.vm.define "mstr01" do |mstr01|
    #snn01.customize ["modifyvm", :id, "--memory", 2048]
    snn01.vm.box = "bento/centos-6.7"
    snn01.vm.hostname = "snn01"
    #mstr01.vm.hostname = "mstr01"
    #mtrr01.vm.box = "wharton-wcit/centos6py36"
    snn01.vm.network "private_network", ip: "192.168.60.161"
#   snn01.vm.provision "shell" do |s|
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari ambari.local' >> /etc/hosts"
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01 nn01.local' >> /etc/hosts"
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01 snn01.local' >> /etc/hosts"
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01 dn01.local' >> /etc/hosts"
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02 dn02.local' >> /etc/hosts"
    snn01.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03 dn03.local' >> /etc/hosts"
  end
  config.vm.define "dn01" do |dn01|
    #dn01.customize ["modifyvm", :id, "--memory", 2048]
    dn01.vm.box = "bento/centos-6.7"
    dn01.vm.hostname = "dn01"
    #dn01.vm.box = "wharton-wcit/centos6py36"
    dn01.vm.network "private_network", ip: "192.168.60.165"
#   dn01.vm.provision :shell,
#   dn01.vm.provision "shell" do |s|
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari ambari.local' >> /etc/hosts"
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01 nn01.local' >> /etc/hosts"
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01 snn01.local' >> /etc/hosts"
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01 dn01.local' >> /etc/hosts"
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02 dn02.local' >> /etc/hosts"
    dn01.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03 dn03.local' >> /etc/hosts"
  end
  config.vm.define "dn02" do |dn02|
    #dn02.customize ["modifyvm", :id, "--memory", 2048]
    dn02.vm.box = "bento/centos-6.7"
    dn02.vm.hostname = "dn02"
    #dn02.vm.box = "wharton-wcit/centos6py36"
    dn02.vm.network "private_network", ip: "192.168.60.166"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari ambari.local' >> /etc/hosts"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01 nn01.local' >> /etc/hosts"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01 snn01.local' >> /etc/hosts"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01 dn01.local' >> /etc/hosts"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02 dn02.local' >> /etc/hosts"
    dn02.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03 dn03.local' >> /etc/hosts"
  end
  config.vm.define "dn03" do |dn03|
    dn03.vm.box = "bento/centos-6.7"
    dn03.vm.hostname = "dn03"
    #dn03.vm.box = "wharton-wcit/centos6py36"
    dn03.vm.network "private_network", ip: "192.168.60.167"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.159 ambari ambari.local' >> /etc/hosts"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.160 nn01 nn01.local' >> /etc/hosts"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.161 snn01 snn01.local' >> /etc/hosts"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.165 dn01 dn01.local' >> /etc/hosts"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.166 dn02 dn02.local' >> /etc/hosts"
    dn03.vm.provision "shell", :inline => "sudo echo '192.168.60.167 dn03 dn03.local' >> /etc/hosts"
  end
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
