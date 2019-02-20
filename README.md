# d-kern-mod-vm
VM used for developing a kernel module in the D programming language

## Setting up the environment

This setup requires `vagrant`, `vitualbox` and `ansible` to be installed on the host OS.

### Vagrant

To install `vagrant` follow the [instructions](https://www.vagrantup.com/docs/installation/) on their website.

| WARNING: Beware of system package managers! Some operating system distributions include a vagrant package in their upstream package repos. Please do not install Vagrant in this manner. Typically these packages are missing dependencies or include very outdated versions of Vagrant. If you install via your system's package manager, it is very likely that you will experience issues. Please use the official installers on the downloads page.
| --- |

[Download](https://www.vagrantup.com/downloads.html) and install `vagrant`.

```
$ wget https://releases.hashicorp.com/vagrant/2.2.3/vagrant_2.2.3_x86_64.deb
$ sudo dpkg -i vagrant_2.2.3_x86_64.deb
$ sudo apt-get install -f
$ vagrant plugin install vagrant-disksize
$ vagrant plugin install vagrant-reload
```

### Ansible

Install as [instructed](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html#latest-releases-via-apt-ubuntu).

```
$ sudo apt-get update
$ sudo apt-get install software-properties-common
$ sudo apt-add-repository --yes --update ppa:ansible/ansible
$ sudo apt-get install ansible
```

### Virtualbox

[Download](https://www.virtualbox.org/wiki/Linux_Downloads) and install.

```
$ wget https://download.virtualbox.org/virtualbox/6.0.4/virtualbox-6.0_6.0.4-128413~Ubuntu~bionic_amd64.deb
$ sudo dpkg -i virtualbox-6.0_6.0.4-128413~Ubuntu~bionic_amd64.deb
$ sudo apt-get install -f
```

## Powering on the VM

```
$ git clone https://github.com/edi33416/d-kern-mod-vm.git
$ cd d-kern-mod-vm/vagrantfile
$ vagrant up
```

Running `vagrant up` will power up an `Ubuntu 18.04` VM and it will provision it as per the ansile scripts.
After it's done, run `vagrant ssh` to ssh into your fresh VM.
