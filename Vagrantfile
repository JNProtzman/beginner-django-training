# -*- mode: ruby -*-
# vi: set ft=ruby :

# All Vagrant configuration is done below. The "2" in Vagrant.configure
# configures the configuration version (we support older styles for
# backwards compatibility). Please don't change it unless you know what
# you're doing.
Vagrant.configure("2") do |config|
  # The most common configuration options are documented and commented below.
  # For a complete reference, please see the online documentation at
  # https://docs.vagrantup.com.

  # Every Vagrant development environment requires a box. You can search for
  # boxes at https://atlas.hashicorp.com/search.
  config.vm.box = "ubuntu/jammy64"

  config.vm.network "forwarded_port", guest: 8080, host: 8080

  config.vm.provision "shell", inline: <<-SHELL
    sudo apt-get update
    sudo apt-get install -y python3-venv zip python3-pip
    touch /home/vagrant/.bash_aliases
    if ! grep -q PYTHON_ALIAS_ADDED /home/vagrant/.bash_aliases; then
        echo "# PYTHON_ALIAS_ADDED" >> /home/vagrant/.bash_aliases
        echo "alias python='python3'" >> /home/vagrant/.bash_aliases
    fi
  SHELL
end


"""
INITIAL PROJECT SETUP IN VAGRANT

cd /vagrant

# Create a virtual env
python -m venv ~/env

# Activate the virtualenv
source ~/env/bin/activate

# Install requirements
python3 -m pip install -r requirements.txt

# Run the server on the port you want to run it on
python3 manage.py runserver 0.0.0.0:8080
"""
