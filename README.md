# mgmt-playground
This is an Ansible project with a development environment powered by Vagrant.

This project sets up:

* 3 virtual machines with Fedora/25-cloud-base

This project is intended as a demo/playground for a mgmt-introductory , teaching git, vagrant and ansible, in de most simple way, and still useable in my classroom. Surely , this playbook can still be improved, but this way it is manageable in my classroom with my students.

## Dependencies

I use as host a Fedora/25-cloud-base machine, make sure you have installed :

- vagrant
- vagrant-libvirt
- vagrant-hostmanager
- ansible (ver. 2+)
- git

And enabled nested KVM

```ShellSession
$ sudo modprobe -r kvm_intel
$ sudo modprobe kvm_intel nested=1
```
view state nested KVM

```ShellSession
$ cat /sys/module/kvm_intel/parameters/nested
```

## Getting started

When cloning, choose a more suiteable  name for the target directory!

```ShellSession
$ git clone https://github.com/belbob/mgmt-playground.git my-mgmt-playground
```
After cloning, it's best to remove the `.git` directory and initialise a new repository. The history of the code is most probably irrelevant for your mgmt-playground project...

### Installation opennebula-cluster

Open a terminal, go to a suitable directory to store this project and issue the following commands:

create the first mgmt-vm

```ShellSession
$ vagrant up mgmt1
```

after finishing mgmt1 you can start the other vms

```ShellSession
$ vagrant up mgmt2
```
and
```ShellSession
$ vagrant up mgmt3
```

## some issues


## Contributing

Issues, feature requests, ideas are appreciated and can be posted in the Issues section. Pull requests are also very welcome. Preferably, create a topic branch and when submitting, squash your commits into one (with a descriptive message).

## License

Licensed under the "GNU GENERAL PUBLIC LICENSE Version 3, 29 June 2007". See [LICENSE.md](/License.md) for details.

## Author Information

Written by Robert Keersse (robert.keersse@gmail.com)

Contributions by:

-
