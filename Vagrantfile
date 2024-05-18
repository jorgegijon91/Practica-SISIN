Vagrant.configure("2") do |config|
  
  # Introduce aquí la configuración del servidor virtual
  config.vm.box = "ubuntu/xenial64" # Configuración de la box
  config.vm.network "private_network", ip: "192.168.50.55" #Configuración de la red
  config.vm.synced_folder ".", "/practica_jorge" # Sincronización de carpetas

  config.vm.provision "shell", inline: <<-SHELL

      #Instalamos el servidor web, actualizando previamente
      sudo apt update  
       
      sudo apt install -y nginx
      #Reiniciar y aplicar cambios
      sudo systemctl restart -y nginx
      # Instalación de los binarios de PHP, el driver mysqli y la extensión FPM para realizar peticiones de tipo RESTful
      sudo apt-get install php php-mysqli
      sudo apt-get install php7.0-fpm

      # Generar archivo SQL con los registros de los diferentes Módulos Profesionales
      echo "-- Insertar datos de ejemplo en la tabla 'modulos'" > /home/vagrant/datos_modulos.sql
      echo "INSERT INTO gestion_modulos_profesionales.modulos(Horario, Lunes, Martes, Miercoles, Jueves, Viernes) VALUES" >> /home/vagrant/datos_modulos.sql
      echo "('8:15-9:10', 'FOL', 'SISIN', 'BADAT', 'BADAT', 'SISIN')," >> /home/vagrant/datos_modulos.sql   
      echo "('9:10-10:05', 'PRO', 'LMSGI', 'BADAT', 'LEUP', 'BADAT')," >> /home/vagrant/datos_modulos.sql
      echo "('10:05-11:00', 'BADAT', 'LMSGI', 'PRO', 'LEUP', 'ENDES')," >> /home/vagrant/datos_modulos.sql
      echo "('11:30-12:25', 'BADAT', 'ENDES', 'LMSGI', 'PRO', 'ENDES')," >> /home/vagrant/datos_modulos.sql
      echo "('12:25-13:20', 'SISIN', 'PRO', 'LMSGI', 'PRO', 'PRO')," >> /home/vagrant/datos_modulos.sql
      echo "('13:20-14:15', 'SISIN', 'FOL', 'FOL', 'SISIN', 'PRO')" >> /home/vagrant/datos_modulos.sql

  SHELL

end
