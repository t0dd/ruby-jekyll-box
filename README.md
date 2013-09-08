## **Originally forked from rails/rails-dev-box repo and reconfigured.**

# A Virtual Machine for Ruby and Jekyll Development

## Introduction

This project automates the setup of a development environment for working in Ruby and the Jekyll static site generator.


## Requirements

* [VirtualBox](https://www.virtualbox.org)

* [Vagrant 1.1+](http://vagrantup.com)

## What's In The Box

* Git

* RVM

* Ruby 2.0.0 (binary RVM install)

* Bundler

* Jekyll

## How To Build The Virtual Machine

Building the virtual machine is this easy:

    download & extract to project directory

    or clone to local machine
    host $ git clone https://github.com/t0dd/ruby-jekyll-box.git
    host $ vagrant up

If the base box is not present that command fetches it first. 
The setup itself takes a few minutes. 
After the installation has finished, you can access the virtual machine with:

    host $ vagrant ssh
    Welcome to Ubuntu 12.04 LTS (GNU/Linux 3.2.0-23-generic-pae i686)
    ...
    vagrant@ruby-jekyll-box:~$

Port 4000 in the host computer is forwarded to port 4000 in the virtual machine. 
Thus, applications running in the virtual machine can be accessed via localhost:4000 in the host computer.



## Recommended Workflow

The recommended workflow is

* edit in the host computer and
* test within the virtual machine.

Vagrant mounts the directory as _/vagrant_ within the virtual machine:

This workflow is convenient because in the host computer you normally have your editor of choice fine-tuned, Git configured, and SSH keys in place.

## How To Use The Virtual Machine with Jekyll

Once you have connected into the guest box via ssh, change to the /vagrant directory to sync your project with your local machine.

    vagrant@ruby-jekyll-box:~$ cd /vagrant

You can create a new jekyll project with all of the required files and directories by entering:

    vagrant@ruby-jekyll-box:~$ jekyll new sitename

(you can replace sitename with the name of your project)

Move to your jekyll directory to run it later.

    vagrant@ruby-jekyll-box:~$ cd ./sitename

Open the project folder on your local machine to begin editing the files.

You can test your jekyll site by running 

    vagrant@ruby-jekyll-box:~$ jekyll serve
    
then open a local browser and go to localhost:4000 to view the site.

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
