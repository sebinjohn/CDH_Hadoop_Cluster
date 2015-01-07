Containerize a CDH Cluster
==================

This is a test to containerize CDH Cluster. This fig file brings up 3 containers
* MySQL Container : data in non persistant
* Cloudera Manager Server
* Cloudera Manager Agent

Further development is needed, like opening some ports in agent to install Hadoop in the cluster
formed by the agent containers. This work is going on

```
  git clone https://github.com/sebinjohn/CDH_Hadoop_Cluster.git
  cd CDH_Hadoop_Cluster/
  fig up
```
``fig ps`` gives the list of running container names

open ``http://<cmserver_ip>:7180/ ``

```
username : admin
password : admin
```
To scale to N number of agents : ``fig scale cmagent=N``

If you want to persist the data in mysql, open the fig.yml and add the below 2 lines unders <b>mysqltest:</b>

```
  volumes:
     - <Data Dir>:/var/lib/mysql
```

Replace Data_Dir with an existing empty directory

Dockerfile for cloudera manager server is available <a href="https://github.com/sebinjohn/cloudera_manager">here</a>

Dockerfile for cloudera agent is available <a href="https://github.com/sebinjohn/cloudera_agent">here</a>

Prerequisite
====================

fig and docker should be installed in your system.

The code has been tested using ubuntu14.04 vagrant image See the Vagrantfile
