## Ruby on Rails Vagrant Box
This is a Ruby on Rails Vagrant box running on Ubuntu 12.04LTS.

###Getting Started
- Install git (http://git-scm.com/) for free.
- Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads) for free.
- Install the latest version of [Vagrant](http://downloads.vagrantup.com/) for free.
- Clone this repo and vagrant up

###Rubymine Setup

- go to options (command+,)
- search SDK in options,
- click Add SDK / new remote
- click Fill from Vagrant config and select the folder where your Vagrantfile is located
- Very important: In the field Ruby interpreter path, put /home/vagrant/.rbenv/versions/2.****/bin/ruby (your ruby version may change, check your versions with ls /home/vagrant/.rbenv/versions in your guest machine
- Click OK, grab a cofee
- You're done
http://stackoverflow.com/questions/19662203/configure-rubymine-with-vagrant-and-rbenv

```bash
$ git clone https://github.com/inrivagmbh/rails-vagrant.git
$ cd rails-vagrant
$ vagrant up
```
- Wait for some time while Vagrant downloads the Ubuntu server image and automatically sets up your new Rails development environment.
- When everything is finished, visit http://10.0.33.36/ in your browser to see the Rails test page.

###Other Details
- There is a default project created in /var/www on your new guest machine (which is symlinked to /vagrant/www on your guest machine or rails-vagrant/www on your host machine).
- It's probably nicer if you edit your hosts to set up a domain to point to 10.0.33.36 for easier access.
- The environment on the default project is set to 'development'
- This build uses [rbenv](https://github.com/sstephenson/rbenv) instead of rvm.
- To create a new Rails project:

```bash
rails-vagrant markdunphy$ vagrant ssh # SSH into the guest machine
vagrant@precise32:~$ sudo su # Gain root
root@precise32:/home/vagrant# rails new /vagrant/www/new-project-name-here # Create new project
```

###Contributing
- Feel free to make a pull request (fork, branch, pull) adding something to the bootstrap.sh file to add new functionality. I'll most likely accept it.
