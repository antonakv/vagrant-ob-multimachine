
Vagrant.configure("2") do |config|
  config.vm.box = "aakulov/nginx64"
  (1..2).each do |i|
    config.vm.define "web#{i}" do |web|
      config.vm.hostname = "web#{i}"
      web.vm.network "private_network", ip: "192.168.101.#{100+i}"
    end
  end
end