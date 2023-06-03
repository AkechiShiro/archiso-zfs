Vagrant.configure("2") do |config|
    config.vm.box = "archlinux/archlinux"

    config.vm.define 'archlinux'

    config.ssh.insert_key = true
    config.ssh.private_key_path = ["~/.ssh/id_rsa", "~/.vagrant.d/insecure_private_key"]
    config.vm.provision "file", source: "~/.ssh/id_rsa.pub", destination: "~/.ssh/authorized_keys"
    config.ssh.username = "vagrant"
    config.ssh.password = "vagrant"

    # Prevent SharedFoldersEnableSymlinksCreate errors
    config.vm.synced_folder ".", "/vagrant", disabled: true
end
