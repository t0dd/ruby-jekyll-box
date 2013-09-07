# Originally forked from rails/rails-dev-box repo and reconfigured.

# A Virtual Machine for Ruby and Jekyll Development

## Introduction

This project automates the setup of a development environment for working in Ruby and the Jekyll static site generator.


## Requirements

* [VirtualBox](https://www.virtualbox.org)

* [Vagrant 1.1+](http://vagrantup.com)

## How To Build The Virtual Machine

Building the virtual machine is this easy:

    extract to project directory
    host $ vagrant up

If the base box is not present that command fetches it first. 
The setup itself takes a few minutes. 
After the installation has finished, you can access the virtual machine with:

    host $ vagrant ssh
    Welcome to Ubuntu 12.04 LTS (GNU/Linux 3.2.0-23-generic-pae i686)
    ...
    vagrant@rails-dev-box:~$

Port 4000 in the host computer is forwarded to port 4000 in the virtual machine. 
Thus, applications running in the virtual machine can be accessed via localhost:4000 in the host computer.

## What's In The Box

* Git

* RVM

* Ruby 2.0.0 (binary RVM install)

* Bundler

* Jekyll


## Recommended Workflow

The recommended workflow is

* edit in the host computer and

* test within the virtual machine.

Just clone your Rails fork in the directory of the development box in the host computer:

Vagrant mounts the directory as _/vagrant_ within the virtual machine:

We are ready to go to edit in the host, and test in the virtual machine.

This workflow is convenient because in the host computer you normally have your editor of choice fine-tuned, Git configured, and SSH keys in place.

## Virtual Machine Management

When done just log out with `^D` and suspend the virtual machine

    host $ vagrant suspend

then, resume to hack again

    host $ vagrant resume

Run

    host $ vagrant halt

to shutdown the virtual machine, and

    host $ vagrant up

to boot it again.

You can find out the state of a virtual machine anytime by invoking

    host $ vagrant status

Finally, to completely wipe the virtual machine from the disk **destroying all its contents**:

    host $ vagrant destroy # DANGER: all is gone

Please check the [Vagrant documentation](http://vagrantup.com/v1/docs/index.html) for more information on Vagrant.
