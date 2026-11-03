
Vagrant.configure("2") do |config|

  # -------------------------
  # Database VM
  # -------------------------
  config.vm.define "db01" do |db|
    db.vm.box = "eurolinux-vagrant/centos-stream-9"
    db.vm.box_version = "9.0.43"
    db.vm.hostname = "db01"
    db.vm.network "private_network", ip: "192.168.56.15"

    db.vm.provider "virtualbox" do |vb|
      vb.memory = 2048
      vb.cpus = 1
    end
  end

  # -------------------------
  # Memcached VM
  # -------------------------
  config.vm.define "mc01" do |mc|
    mc.vm.box = "eurolinux-vagrant/centos-stream-9"
    mc.vm.box_version = "9.0.43"
    mc.vm.hostname = "mc01"
    mc.vm.network "private_network", ip: "192.168.56.14"

    mc.vm.provider "virtualbox" do |vb|
      vb.memory = 1024
      vb.cpus = 1
    end
  end

  # -------------------------
  # RabbitMQ VM
  # -------------------------
  config.vm.define "rmq01" do |rmq|
    rmq.vm.box = "eurolinux-vagrant/centos-stream-9"
    rmq.vm.box_version = "9.0.43"
    rmq.vm.hostname = "rmq01"
    rmq.vm.network "private_network", ip: "192.168.56.13"

    rmq.vm.provider "virtualbox" do |vb|
      vb.memory = 1024
      vb.cpus = 1
    end
  end

  # -------------------------
  # Application VM
  # -------------------------
  config.vm.define "app01" do |app|
    app.vm.box = "eurolinux-vagrant/centos-stream-9"
    app.vm.box_version = "9.0.43"
    app.vm.hostname = "app01"
    app.vm.network "private_network", ip: "192.168.56.12"

    app.vm.provider "virtualbox" do |vb|
      vb.memory = 6144
      vb.cpus = 2
    end
  end

  # -------------------------
  # Nginx Web VM
  # -------------------------
  config.vm.define "web01" do |web|
    web.vm.box = "ubuntu/jammy64"
    web.vm.hostname = "web01"
    web.vm.network "private_network", ip: "192.168.56.11"

    web.vm.provider "virtualbox" do |vb|
      vb.memory = 1024
      vb.cpus = 1
    end
  end

end
