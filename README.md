# basic-telegraf-setup

A quick `docker-compose` setup to test `telegraf` with `grafana` and `influxdb`.

## Usage

* Start all the containers with: `docker-compose up`

* Navigate your brower to: `http://localhost:4000/`
* Use the username/password: `foobar/foobar`
* Select the `System` dashboard

## Preview

![Telegraf](/img/Grafana-System_example_screenshot.png?raw=true "Telegraf")


## RUN
sudo docker-compose up -d


## Vagrant

Another approach is to use [Vagrant](http://www.vagrantup,com) and [VirtualBox](https://www.virtualbox.org/) to create a virtual machine. This way the setting up of the environment is completely automated. You can use the following steps:
- Install [Vagrant](http://www.vagrantup,com) and [VirtualBox](https://www.virtualbox.org/)
- Install the [vagrant-docker-compose](https://github.com/leighmcculloch/vagrant-docker-compose) plugin using the command line: `vagrant plugin install vagrant-docker-compose`  
- Use this [Vagrantfile](https://raw.githubusercontent.com/perfana/perfana/master/Vagrantfile) to generate a box. Place file in a directory of your choosing and use command line in that directory: `vagrant up`.  

> shortcut using curl: `curl -O https://raw.githubusercontent.com/perfana/perfana/master/Vagrantfile && vagrant up`  
