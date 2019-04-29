Vagrant.configure("2") do |config|
  #Usar box que tinguem
  config.vm.box = "generic/ubuntu1804"
  config.vm.network "forwarded_port", guest:80 , host:8080
  #Normalment no cal ja que ja esta configurat
  config.vm.synced_folder ".","/vagrant"
  config.vm.provision "shell", inline:<<-SHELL
  sudo apt update
  sudo apt install -y apache2         # Amb la -y diem que dongui yes
  sudo hostanemctl set-homename webserver
  sudo ln -fs /vagrantScript/web/ /var/www/html/
  SHELL
end
