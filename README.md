# Perfana demo

A `docker-compose` setup to run a `Perfana` demo environment.

## Start

* Start all the containers with: `sudo docker-compose up -d`

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


## Vagrant

Another approach is to use [Vagrant](http://www.vagrantup.com) and [VirtualBox](https://www.virtualbox.org/) to create a virtual machine. This way the setting up of the environment is completely automated. You can use the following steps:
- Install [Vagrant](http://www.vagrantup,com) and [VirtualBox](https://www.virtualbox.org/)
- Install the [vagrant-docker-compose](https://github.com/leighmcculloch/vagrant-docker-compose) plugin using the command line: `vagrant plugin install vagrant-docker-compose`  
- Use this [Vagrantfile](https://raw.githubusercontent.com/perfana/perfana-test-env/master/Vagrantfile) to generate a box. Place file in a directory of your choosing and use command line in that directory: `vagrant up`.  

> shortcut using curl: `curl -O https://raw.githubusercontent.com/perfana/perfana-test-env/master/Vagrantfile && vagrant up`  

## Demo instructions
* Open Perfana dashboard at ```http://localhost:3000```
* Sign in with user/paswword admin@example.com/admin
* Click "Grafana configuration" in the sidebar
* Click  "Sync all Grafana instance dashboards" (refresh icon). This should sync Perfana with the Grafana instance running at ```http://localhost:4000```
* Go the Jenkins at ```http://localhost:8080```, and build job "PERFANA-GATLING-DEMO". The test run should should show up in Perfana! Run the build a few times to check out the benchmark features of Perfana.
