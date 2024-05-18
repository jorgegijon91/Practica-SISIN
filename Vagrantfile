Vagrant.configure("2") do |config|
  
  # Introduce aquí la configuración del servidor virtual
  config.vm.box = "ubuntu/xenial64" # Configuración de la box
  config.vm.network "private_network", ip: "192.168.50.55" #Configuración de la red
  config.vm.synced_folder ".", "/practica_jorge" # Sincronización de carpetas

  config.vm.provision "shell", inline: <<-SHELL

      # Instalación de los binarios de PHP, el driver mysqli y la extensión FPM para realizar peticiones de tipo RESTful


      # Generar archivo SQL con los registros de los diferentes Módulos Profesionales
      

  SHELL

end
