Vagrant.configure("2") do |config|
  config.vm.define "hdptest" do |hdprepo|
    hdprepo.vm.box = "bento/centos-6.7"
    hdprepo.vm.hostname = "hdptest"
    #hdprepo.vm.box = "wharton-wcit/centos6py36"
    hdprepo.vm.network "private_network", ip: "192.168.60.162"
  end
  config.vm.define "hdprepo" do |hdprepo|
    hdprepo.vm.box = "bento/centos-6.7"
    hdprepo.vm.hostname = "hdprepo"
    #hdprepo.vm.box = "wharton-wcit/centos6py36"
    hdprepo.vm.network "private_network", ip: "192.168.60.161"
  end
  config.vm.define "mstr01" do |mstr01|
    mstr01.vm.box = "bento/centos-6.7"
    mstr01.vm.hostname = "mstr01"
    #mtrr01.vm.box = "wharton-wcit/centos6py36"
    mstr01.vm.network "private_network", ip: "192.168.60.160"
  end
  config.vm.define "slv01" do |slv01|
    slv01.vm.box = "bento/centos-6.7"
    slv01.vm.hostname = "slv01"
    #slv01.vm.box = "wharton-wcit/centos6py36"
    slv01.vm.network "private_network", ip: "192.168.60.165"
  end
  config.vm.define "slv02" do |slv02|
    slv02.vm.box = "bento/centos-6.7"
    slv02.vm.hostname = "slv02"
    #slv02.vm.box = "wharton-wcit/centos6py36"
    slv02.vm.network "private_network", ip: "192.168.60.166"
  end
  config.vm.define "slv03" do |slv03|
    slv03.vm.box = "bento/centos-6.7"
    slv03.vm.hostname = "slv03"
    #slv03.vm.box = "wharton-wcit/centos6py36"
    slv03.vm.network "private_network", ip: "192.168.60.167"
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
