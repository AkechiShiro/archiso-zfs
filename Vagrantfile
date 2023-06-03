Vagrant.configure("2") do |config|
    config.vm.box = "archlinux/archlinux"
    config.vm.cloud_init :user_data, content_type: "text/cloud-config", path: "cloud-init.yml"

    config.vm.define 'archlinux'

    config.ssh.username = "arch"
    config.ssh.insert_key = true
    #config.ssh.password = "password"

    # Prevent SharedFoldersEnableSymlinksCreate errors
    config.vm.synced_folder ".", "/vagrant", disabled: true
    # Provision project.
    config.vm.provision "shell", inline: <<-SHELL
        pacman -Syu --noconfirm
        cat /etc/passwd
        cat /home/arch/.ssh/id_*
    SHELL
end
