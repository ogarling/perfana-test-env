# Perfana demo

A `docker-compose` setup to run a `Perfana` demo environment.

## Usage

* Start all the containers with: `docker-compose up`

The end result will be an environment with the following started docker containers:

| Container  	| Description                                            	| Exposed port|
|------------	|--------------------------------------------------------	|-------	|
| Perfana 	  | Performance dashboard application                      	| 3000    	|
| Grafana 	  | Monitoring dashboard application                      	| 4000    	|
| mongodb    	| Database to store dashboard configurations           		 | 27017 	|
| graphite   	| Time based metrics store                              	| 8070 / 2004 /8125  	|
| jenkins    	| CI server to start demo scripts     	                   | 8080  	|
| mean       	| Demo application to run performance tests against 	     | 3001  	|
| influxdb      | Time based metrics store                          	| 8086 / 2003      |
| telegraf    	|    Metric collection agent 	| -   |
| prometheus      	| Time based metrics store                     	| 9090      |
| node exporter    	|    Exporter for machine metrics  	| -   |
| cadvisor    	|    Analyzes resource usage and performance characteristics of running containers 	| -   |


## RUN
sudo docker-compose up -d

## Vagrant

Another approach is to use [Vagrant](http://www.vagrantup,com) and [VirtualBox](https://www.virtualbox.org/) to create a virtual machine. This way the setting up of the environment is completely automated. You can use the following steps:
- Install [Vagrant](http://www.vagrantup,com) and [VirtualBox](https://www.virtualbox.org/)
- Install the [vagrant-docker-compose](https://github.com/leighmcculloch/vagrant-docker-compose) plugin using the command line: `vagrant plugin install vagrant-docker-compose`  
- Use this [Vagrantfile](https://raw.githubusercontent.com/perfana/perfana-test-env/master/Vagrantfile) to generate a box. Place file in a directory of your choosing and use command line in that directory: `vagrant up`.  

> shortcut using curl: `curl -O https://raw.githubusercontent.com/perfana/perfana-test-env/master/Vagrantfile && vagrant up`  
