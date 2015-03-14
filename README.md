# Overview
A simple Vagrant recipe that sets up a development environment suitable for yarrow development.

## Installation
1. enable virtualization in the bios, if supported
2. install [VirtualBox](https://www.virtualbox.org/)
3. install [Vagrant](http://www.vagrantup.com/)
4. clone this project via Git
5. open a command shell and cd into the project directory
6. type *vagrant status* to verify your installation
7. type *vagrant up* to begin building your development VM
8. once Vagrant has completed, log into your machine with the default password of *vagrant*

## TODO
* Use Ansible to provision box(s)
* Install docker -- on desktop box, or create dedicated docker VM?
