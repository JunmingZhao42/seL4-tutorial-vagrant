# seL4-tutorial-vagrant
This repository provides a Vagrantfile and instructions for setting up a Vagrant box specifically designed for the [seL4 tutorial](https://github.com/seL4/sel4-tutorials).

The Vagrant box allows users to easily create a pre-configured virtual machine environment that includes all the necessary dependencies and tools to follow along with the seL4 tutorial.


## Requirements

To use this Vagrant box, you need to have the following software installed on your local machine:

- [Vagrant](https://www.vagrantup.com/downloads): A tool for building and managing virtual machine environments.
- [VirtualBox](https://www.virtualbox.org/wiki/Downloads): A virtualization software that runs on top of your operating system.

## Usages

To get started with the seL4 tutorial using this Vagrant box, follow these steps:

1. Clone this repository to your local machine:
```sh
git clone https://github.com/JunmingZhao42/seL4-tutorial-vagrant.git
cd seL4-tutorial-vagrant
```

2. Start the vagrant box:
```
vagrant up
```
This command will download the Vagrant box, create a new virtual machine, and provision it with the necessary dependencies and tools.

3. Once the Vagrant box is up and running, you can connect to it via SSH:
```
vagrant ssh
```
This will open an SSH session into the virtual machine.

Alternatively, you can check the machine's `ssh-config` via:
```
vagrant ssh-config
```
Copy-paste the `ssh-config` output to your local `.ssh/config` file and you can access the machine via VSCode or other editors.

4. Inside the virtual machine, you can navigate to the seL4 tutorial directory and start following [seL4-tutorial](https://docs.sel4.systems/Tutorials/#the-tutorials):
```sh
cd sel4-tutorials-manifest
./init --tut hello-world
cd hello-world_build
ninja
./simulate
```

5. To stop the virtual machine:
```
vagrant halt
```

6. To completely remove the Vagrant box and free up disk space, run:
```
vagrant destroy
```
