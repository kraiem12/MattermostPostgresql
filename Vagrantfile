Vagrant.configure("2") do |config|

  # Linux OS CentOS
  config.vm.box = "geerlingguy/centos7"
  config.vm.provider :virtualbox do |v|
      v.memory = 500
      v.linked_clone = true
  end

  # Application server
  config.vm.define "postgers" do |postgres|
    postgres.vm.hostname = "postgres"
    # static ip address
    postgres.vm.network :private_network, ip: "192.168.60.20"
  end
  config.vm.define "mattermost" do |mattermost|
    mattermost.vm.hostname = "mattermost"
    # static ip address
    mattermost.vm.network :private_network, ip: "192.168.60.21"
  end  
  config.vm.define "nginx" do |nginx|
    nginx.vm.hostname = "nginx"
    # static ip address
    nginx.vm.network :private_network, ip: "192.168.60.22"
  end

end
