Vagrant.configure("2") do |config|


   config.vm.define "automation" do |manager|
    manager.vm.box = "centos/7"
        manager.vm.network "private_network", ip: "192.168.33.150"
	manager.vm.hostname = "automation.dexter.com.br" 
       config.vm.provider "virtualbox" do |vb|
        vb.memory = "4256"
        end



        end



   config.vm.define "devops" do |worker1|
    worker1.vm.box = "ubuntu/xenial64"
        worker1.vm.network "private_network", ip: "192.168.33.151"
	worker1.vm.hostname = "devops.dexter.com.br" 

       config.vm.provider "virtualbox" do |vb|
        vb.memory = "4196"
        end
  end


   config.vm.define "docker" do |worker2|
    worker2.vm.box = "ubuntu/xenial64"
        worker2.vm.network "private_network", ip: "192.168.33.152"
	worker2.vm.hostname = "docker.dexter.com.br" 

       config.vm.provider "virtualbox" do |vb|
        vb.memory = "1024"
        end
end

   config.vm.provision "shell", inline: <<-SHELL
	echo "192.168.33.150 automation.dexter.com.br "  >>  /etc/hosts 
	echo "192.168.33.151 devops.dexter.com.br "  >>  /etc/hosts 
	echo "192.168.33.152 docker.dexter.com.br "  >>  /etc/hosts 
 	echo "ssh-rsa AAAAB3NzaC1yc2EAAAADAQABAAABAQDBha9I7M5JwwFxu2X0jJRcvvfG7Gla6H0VaevoglLE+hfWS4CWeBsA6cpPopp7SiArjyqfVcUxTdHookqDE1JJ6S1iZTjOPdrG1B6DEHCJ8rNPb72UdmaZFiQLnGcwBTsQTYYoUQ4VqKiaWxk8FNYdmnTIs/d0S3xtI1mhMLRFGcSz+Pa4wxOe6cokxoFNjxeFsKZG5yUJE2/tvpx7kC2LdJUmyD5T6TeQumXyX4Iy148gevoTmCM9d6BFO6hCOa3Or62Z9kDmCoiJjhwb5cVZfbEKbnSSUyayTk+9GcaJ5QCueKrf70sotBDqeSleCkNLkx7JUT/YlLN7/mJAIxaP" >> /home/vagrant/.ssh/authorized_keys	



	SHELL

end





