# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|
    config.vagrant.host = :detect

    config.ssh.forward_agent = false
    config.ssh.forward_x11 = false
    config.ssh.guest_port = 22
    config.ssh.keep_alive = true
    config.ssh.shell = "sh"
    config.ssh.default.username = "web"

    config.vm.usable_port_range = (2200..2250)
    config.vm.box_url = "https://dl.dropboxusercontent.com/u/110582551/slitaz4.0-VB4.3.box"
    config.vm.boot_timeout = 300
    config.vm.graceful_halt_timeout = 60
    config.vm.host_name = nil
    config.vm.guest = :linux
    config.vm.box = "vagrant-slitaz"

    config.vm.network :forwarded_port,
        guest: 22,
        host: 2222,
        host_ip: "127.0.0.1",
        id: "ssh",
        auto_correct: true

    config.vm.network :forwarded_port,
        guest: 80,
        host: 8888,
        host_ip: "127.0.0.1",
        id: "www",
        auto_correct: true

    config.vm.synced_folder ".", "/vagrant", disabled: true
    config.vm.synced_folder ".", "/projects"
    config.vm.synced_folder "./www", "/projects/www"

    config.nfs.map_uid = :auto
    config.nfs.map_gid = :auto

    config.vm.provider :virtualbox do |vb|
        vb.customize [
          "modifyvm", :id,
          "--memory", "1536",
          "--cpus", "2",
          "--ioapic", "on"
          ]

        #vb.gui = true
    end
end
