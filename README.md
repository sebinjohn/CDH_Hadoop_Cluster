CDH_Hadoop_Cluster
==================

This is a test to containerize CDH Cluster

clone this repo and execute
cd CDH_Hadoop_Cluster/
fig up

take the IP address of the cmserver, which runs cloudera manager using docker inspect
go to browser and http://<cmserver_ip>:7180/

username : admin
password : admin

To scale the number of agents to NUM

fig scale cmagent=NUM

If you want to persist the data in mysql, open the fig.yml and add the below 2 lines unders <b>mysqltest:</b>

volumes:
    - <Data Dir>:/var/lib/mysql
    
Replace Data_Dir with an existing empty directory

Prerequisite
====================

fig and docker should be installed in your system.
