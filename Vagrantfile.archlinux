Vagrant.configure("2") do |config|
    config.vm.box = "archlinux/archlinux"

    config.vm.define 'archlinux'

    config.ssh.username = "vagrant"
    config.ssh.password = "vagrant"

    # Prevent SharedFoldersEnableSymlinksCreate errors
    config.vm.synced_folder ".", "/vagrant", disabled: true
end
