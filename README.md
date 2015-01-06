CDH_Hadoop_Cluster
==================

This is a test to containerize CDH Cluster

build the two images first using,

docker build -t cm_server cloudera_manager/
docker build -t cm_agent cloudera_agent/

then run fig up

you can scale or down using fig scale cmagent=number of services you require
