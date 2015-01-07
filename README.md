CDH_Hadoop_Cluster
==================

This is a test to containerize CDH Cluster

build the two images first using,

clone this repo and execute

fig up


Initial run will fail because there is no database is available for cloudera manager
I am working on to fix this issue.

as a workaround, use mysql client to login to mysql database with root as root password
run the following queries

CREATE DATABASE cmf;

GRANT ALL PRIVILEGES ON cmf.* TO 'cmf'@'%' IDENTIFIED BY 'cmf'
GRANT ALL PRIVILEGES ON cmf.* TO 'cmf'@'localhost' IDENTIFIED BY 'cmf'
FLUSH PRIVILEGES

fig kill
docker rm $(docker ps -a -q)
fig up


Prerequisite
====================

fig should be installed in your system.

take the IP address of the cmserver, which runs cloudera manager; go to browser and http://<cmserver_ip>:7180/

username : admin
password : admin

you can scale or down using fig scale cmagent=number of services you require
