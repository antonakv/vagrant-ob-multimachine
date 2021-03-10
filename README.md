# Multi machine web01 web02 in single Vagrantfile
## Intro
This manual is dedicated to create 2 web servers using vagrant virtualbox base ubuntu lts box with nginx package installed. 
Tested on Mac OS X.

## Requirements
- Oracle Virtualbox recent version installed
[VirtualBox installation manual](https://www.virtualbox.org/manual/ch01.html#intro-installing)

- Hashicorp vagrant recent version installed
[Vagrant installation manual](https://learn.hashicorp.com/tutorials/vagrant/getting-started-install)

- git installed
[Git installation manual](https://git-scm.com/download/mac)

- web browser installed
Use web browser bundled in your OS

## Preparation 
- Clone git repository. 

```bash
git clone https://github.com/antonakv/vagrant-ob-multimachine
```

Expected command output looks like this:

```bash
Cloning into 'vagrant-ob-multimachine'...
remote: Enumerating objects: 12, done.
remote: Counting objects: 100% (12/12), done.
remote: Compressing objects: 100% (12/12), done.
remote: Total 12 (delta 1), reused 3 (delta 0), pack-reused 0
Receiving objects: 100% (12/12), done.
Resolving deltas: 100% (1/1), done.
```

- Change folder to vagrant-ob-multimachine

```bash
cd vagrant-ob-multimachine
```

## Provisioning

- In the same folder you were before run 

```bash
vagrant up
```

Sample result

```bash
$ vagrant up
Bringing machine 'web1' up with 'virtualbox' provider...
Bringing machine 'web2' up with 'virtualbox' provider...
==> web1: Importing base box 'aakulov/nginx64'...
==> web1: Matching MAC address for NAT networking...
==> web1: Checking if box 'aakulov/nginx64' version '21.03.02' is up to date...
==> web1: Setting the name of the VM: vagrant-ob-multimachine_web1_1615374734051_64279
Vagrant is currently configured to create VirtualBox synced folders with
the `SharedFoldersEnableSymlinksCreate` option enabled. If the Vagrant
guest is not trusted, you may want to disable this option. For more
information on this option, please refer to the VirtualBox manual:

  https://www.virtualbox.org/manual/ch04.html#sharedfolders

This option can be disabled globally with an environment variable:

  VAGRANT_DISABLE_VBOXSYMLINKCREATE=1

or on a per folder basis within the Vagrantfile:

  config.vm.synced_folder '/host/path', '/guest/path', SharedFoldersEnableSymlinksCreate: false
==> web1: Clearing any previously set network interfaces...
==> web1: Preparing network interfaces based on configuration...
    web1: Adapter 1: nat
    web1: Adapter 2: hostonly
==> web1: Forwarding ports...
    web1: 22 (guest) => 2222 (host) (adapter 1)
==> web1: Booting VM...
==> web1: Waiting for machine to boot. This may take a few minutes...
    web1: SSH address: 127.0.0.1:2222
    web1: SSH username: vagrant
    web1: SSH auth method: private key
    web1: 
    web1: Vagrant insecure key detected. Vagrant will automatically replace
    web1: this with a newly generated keypair for better security.
    web1: 
    web1: Inserting generated public key within guest...
    web1: Removing insecure key from the guest if it's present...
    web1: Key inserted! Disconnecting and reconnecting using new SSH key...
==> web1: Machine booted and ready!
==> web1: Checking for guest additions in VM...
==> web1: Setting hostname...
==> web1: Configuring and enabling network interfaces...
==> web1: Mounting shared folders...
    web1: /vagrant => /Users/aakulov/Documents/Development/Hashicorp/vagrant-ob-multimachine
==> web2: Importing base box 'aakulov/nginx64'...
==> web2: Matching MAC address for NAT networking...
==> web2: Checking if box 'aakulov/nginx64' version '21.03.02' is up to date...
==> web2: Setting the name of the VM: vagrant-ob-multimachine_web2_1615374771751_56943
==> web2: Fixed port collision for 22 => 2222. Now on port 2200.
==> web2: Clearing any previously set network interfaces...
==> web2: Preparing network interfaces based on configuration...
    web2: Adapter 1: nat
    web2: Adapter 2: hostonly
==> web2: Forwarding ports...
    web2: 22 (guest) => 2200 (host) (adapter 1)
==> web2: Booting VM...
==> web2: Waiting for machine to boot. This may take a few minutes...
    web2: SSH address: 127.0.0.1:2200
    web2: SSH username: vagrant
    web2: SSH auth method: private key
    web2: 
    web2: Vagrant insecure key detected. Vagrant will automatically replace
    web2: this with a newly generated keypair for better security.
    web2: 
    web2: Inserting generated public key within guest...
    web2: Removing insecure key from the guest if it's present...
    web2: Key inserted! Disconnecting and reconnecting using new SSH key...
==> web2: Machine booted and ready!
==> web2: Checking for guest additions in VM...
==> web2: Setting hostname...
==> web2: Configuring and enabling network interfaces...
==> web2: Mounting shared folders...
    web2: /vagrant => /Users/aakulov/Documents/Development/Hashicorp/vagrant-ob-multimachine
```

## Check website

- In the Web browser open web1
http://192.168.101.101/
- In the Web browser open web2
http://192.168.101.102/

Sample result
```
Welcome to nginx!
If you see this page, the nginx web server is successfully installed and working. Further configuration is required.

For online documentation and support please refer to nginx.org.
Commercial support is available at nginx.com.

Thank you for using nginx.
```