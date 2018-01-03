Vagrant.configure("2") do |config|
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
  config.vm.define "nn01" do |nn01|
  #config.vm.define "mstr01" do |mstr01|
    nn01.vm.box = "bento/centos-6.7"
    nn01.vm.hostname = "nn01"
    #mstr01.vm.hostname = "mstr01"
    #mtrr01.vm.box = "wharton-wcit/centos6py36"
    nn01.vm.network "private_network", ip: "192.168.60.160"
  end
  config.vm.define "snn01" do |snn01|
  #config.vm.define "mstr01" do |mstr01|
    snn01.vm.box = "bento/centos-6.7"
    snn01.vm.hostname = "snn01"
    #mstr01.vm.hostname = "mstr01"
    #mtrr01.vm.box = "wharton-wcit/centos6py36"
    snn01.vm.network "private_network", ip: "192.168.60.161"
  end
  config.vm.define "dn01" do |dn01|
    dn01.vm.box = "bento/centos-6.7"
    dn01.vm.hostname = "dn01"
    #dn01.vm.box = "wharton-wcit/centos6py36"
    dn01.vm.network "private_network", ip: "192.168.60.165"
  end
  config.vm.define "dn02" do |dn02|
    dn02.vm.box = "bento/centos-6.7"
    dn02.vm.hostname = "dn02"
    #dn02.vm.box = "wharton-wcit/centos6py36"
    dn02.vm.network "private_network", ip: "192.168.60.166"
  end
  config.vm.define "dn03" do |dn03|
    dn03.vm.box = "bento/centos-6.7"
    dn03.vm.hostname = "dn03"
    #dn03.vm.box = "wharton-wcit/centos6py36"
    dn03.vm.network "private_network", ip: "192.168.60.167"
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
