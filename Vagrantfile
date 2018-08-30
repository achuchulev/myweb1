Vagrant.configure("2") do |config|
  config.vm.box = "achuchulev/xenial64"
  config.vm.hostname = "bananas3"

  # we use cd /vagrant to copy travis
  config.vm.provision "shell",inline: "cd /vagrant ; bash scripts/provision.sh"
  config.vm.provision "shell", inline: "cd /vagrant/ops ; inspec exec test/integration/default/"
  config.vm.network "private_network", ip: "192.168.56.56"
  config.vm.network "forwarded_port", guest: 80, host: 8080, auto_correct: "true"

end
