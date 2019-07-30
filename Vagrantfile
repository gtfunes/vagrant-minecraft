Vagrant.configure('2') do |config|
  config.vm.define 'mc-house-server'
  config.vm.box = 'jpbriquet/alpine2docker'
  config.ssh.forward_agent = true
  config.vm.network :forwarded_port, host: 8088, guest: 8088
  config.vm.network :forwarded_port, host: 25565, guest: 25565
  
  config.vm.provider :virtualbox do |p|
    p.memory = 2560
    p.cpus = 2
  end
  
  config.vm.provision 'shell', run: 'once', path: 'provision.sh'
end
