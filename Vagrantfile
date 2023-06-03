$own_ssh_key = <<-SCRIPT
ssh-keygen -q -t ed25519 -N "" -f .ssh/login_ssh
cp .ssh/login_ssh.pub .ssh/authorized_keys 
cp .ssh/login_ssh /vagrant/.
SCRIPT

Vagrant.configure("2") do |config|
    config.vm.box = "archlinux/archlinux"
    config.vm.cloud_init :user_data, content_type: "text/cloud-config", path: "cloud-init.yml"

    config.vm.define 'archlinux'

    config.ssh.username = "arch"
    #config.ssh.password = "password"
    config.ssh.insert_key = false

    # Prevent SharedFoldersEnableSymlinksCreate errors
    config.vm.synced_folder ".", "/vagrant", disabled: true
    # Provision project.
    #config.ssh.private_key_path = [File.expand_path("../login_ssh", __FILE__)] + 
    #  Dir.glob("#{Dir.home}/.vagrant.d/boxes/archlinux/*/virtualbox/vagrant_insecure_key")

    #config.vm.provision "shell", inline: $own_ssh_key, privileged: false
end
