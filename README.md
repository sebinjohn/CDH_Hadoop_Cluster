CDH_Hadoop_Cluster
==================

This is a test to containerize CDH Cluster

clone this repo and execute

fig up

take the IP address of the cmserver, which runs cloudera manager; go to browser and http://<cmserver_ip>:7180/

username : admin
password : admin

you can scale or down using fig scale cmagent=number of services you require

If you want to persist the data in mysql, open the fig.yml and add the below 2 lines unders <b>mysqltest:</b>

volumes:
    - /home/vagrant/mysql_data_dir:/var/lib/mysql

Prerequisite
====================

fig should be installed in your system.
