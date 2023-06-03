Vagrant.configure("2") do |config|
    config.vm.box = "archlinux/archlinux"
    config.vm.cloud_init :user_data, content_type: "text/cloud-config", path: "config.cfg"

    config.vm.define 'archlinux'

    config.ssh.insert_key = true
    config.ssh.username = "arch"
    config.ssh.password = "arch"

    # Prevent SharedFoldersEnableSymlinksCreate errors
    config.vm.synced_folder ".", "/vagrant", disabled: true
end
