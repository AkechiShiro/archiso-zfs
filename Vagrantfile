Vagrant.configure("2") do |config|
    config.vm.box = "archlinux/archlinux"

    config.vm.define 'archlinux'

    config.ssh.insert_key = true
    config.ssh.username = "root"
    #config.ssh.password = "arch"

    # Prevent SharedFoldersEnableSymlinksCreate errors
    config.vm.synced_folder ".", "/vagrant", disabled: true
end
