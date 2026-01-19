# -- mode: ruby --
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

  # Base OS
  config.vm.box = "ubuntu/focal64"

  # Networking
  config.vm.network "private_network", ip: "192.168.56.82"
  config.vm.network "public_network"

  # VM resources
  config.vm.provider "virtualbox" do |vb|
    vb.memory = "2048"
  end

  # Provisioning: Docker & Docker Compose
  config.vm.provision "shell", inline: <<-SHELL
    apt-get update -y
    apt-get install -y ca-certificates curl gnupg

    install -m 0755 -d /etc/apt/keyrings
    curl -fsSL https://download.docker.com/linux/ubuntu/gpg | gpg --dearmor -o /etc/apt/keyrings/docker.gpg
    chmod a+r /etc/apt/keyrings/docker.gpg

    echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] \
    https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo $VERSION_CODENAME) stable" \
    > /etc/apt/sources.list.d/docker.list

    apt-get update -y
    apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

    curl -L https://github.com/docker/compose/releases/download/v2.1.1/docker-compose-$(uname -s)-$(uname -m) \
      -o /usr/local/bin/docker-compose
    chmod +x /usr/local/bin/docker-compose
  SHELL

end
