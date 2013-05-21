cm-api-flume-example
====================

This project provides an example of using Cloudera Manager's Python API Client to create a Flume-NG Service and Agents, and to set and update Agent config files.

More information:  [Flume-NG](http://archive.cloudera.com/cdh4/cdh/4/flume-ng/FlumeUserGuide.html),  [Cloudera Manager](http://www.cloudera.com/content/cloudera/en/products/cloudera-manager.html), [CM API Client](http://cloudera.github.io/cm_api/)




####Requirements
- Cloudera Manager 4.1 or higher (I tested with CM 4.5.2) with at least an HDFS Service running. 
- CM login with Administrator privileges
- CDH 4.1 or higher (I tested with CDH 4.2.1)
- Python (I tested on CentOS 6.4 which includes Python 2.6.6)
- Python SetupTools (see below)
- CM API must be installed (see below)


####Install Python Setup Tools
On CentOS:

    # yum -y install python-setuptools


####Download and Install the CM API Client
Download the CM API Client:

    # wget https://github.com/cloudera/cm_api/tarball/master
    # tar -xvf master

This will give you a dir named something like <code>cloudera-cm_api-1f8dd19<code>

Change to the python directory and install the module (see the README and SHELL_README for additional details):

    # cd cloudera-cm_api-1f8dd19/python
    # python setup.py install

If you feel like it - test the Python Shell:

    # cmps -H <cm-host>
    Enter Username: admin
    Enter Password: 
    Welcome to the Cloudera Manager Console
    Select a cluster using 'show clusters' and 'use'
    cloudera> show clusters
    +------------------+
    |   CLUSTER NAME   |
    +------------------+
    | Cluster 1 - CDH4 |
    +------------------+
    
    cloudera> use Cluster 1 - CDH4
    Connected to Cluster 1 - CDH4
    Cluster 1 - CDH4> status
    +------------+-----------+---------+--------+------------+
    | NAME       | SERVICE   |  STATUS | HEALTH |   CONFIG   |
    +------------+-----------+---------+--------+------------+
    | hue1       | HUE       | STARTED |  GOOD  | UP TO DATE |
    | oozie1     | OOZIE     | STOPPED |  GOOD  | UP TO DATE |
    | hdfs1      | HDFS      | STARTED |  GOOD  | UP TO DATE |
    | impala1    | IMPALA    | STARTED |  GOOD  | UP TO DATE |
    | mapreduce1 | MAPREDUCE | STARTED |  GOOD  | UP TO DATE |
    | hive1      | HIVE      | STARTED |  GOOD  | UP TO DATE |
    +------------+-----------+---------+--------+------------+
    Cluster 1 - CDH4> 

    
