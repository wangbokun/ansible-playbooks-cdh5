ansible-playbooks-cdh5
=========


aws ansible-playbooks-cdh5 hadoop on ec2





HDFS HA,Hive,HTTPFS,Oozie,Pig,Zookeeper,Spark,hue,luancher 



Steps:

1. 修改 hosts in hosts.cdh5 
2. 配置文件修改 groups_var/cdh5-all 
3. 执行 'ansible-playbook -s cdh5.yml -i hosts.cdh5 ' 



rsync配置文件
cdh5-luancher 主机加到 cdh5-all 主机列表中,安装和配置文件同步会跟随base进行，但是不启动服务  


ansible-playbook   -s cdh5.yml   -i us-cdh-hadoop   -t  cdh5-rsync-conf


mail:

wangbokun@ijinshan.com



执行日志：


PLAY [cdh5-all] *************************************************************** 

GATHERING FACTS *************************************************************** 
ok: [10.3.4.253]
ok: [10.3.4.160]
ok: [10.3.4.254]
ok: [10.3.4.161]
ok: [10.3.5.1]
ok: [10.3.5.10]
ok: [10.3.5.3]
ok: [10.3.5.9]
ok: [10.3.5.2]
ok: [10.3.5.5]
ok: [10.3.5.7]
ok: [10.3.5.4]
ok: [10.3.5.11]
ok: [10.3.5.12]

TASK: [create cdh5 repo] ****************************************************** 
changed: [10.3.4.160] => (item=cloudera-cdh544.repo)
changed: [10.3.5.10] => (item=cloudera-cdh544.repo)
changed: [10.3.4.253] => (item=cloudera-cdh544.repo)
changed: [10.3.4.161] => (item=cloudera-cdh544.repo)
changed: [10.3.5.1] => (item=cloudera-cdh544.repo)
changed: [10.3.5.11] => (item=cloudera-cdh544.repo)
changed: [10.3.5.5] => (item=cloudera-cdh544.repo)
changed: [10.3.5.12] => (item=cloudera-cdh544.repo)
changed: [10.3.4.254] => (item=cloudera-cdh544.repo)
changed: [10.3.5.2] => (item=cloudera-cdh544.repo)
changed: [10.3.5.7] => (item=cloudera-cdh544.repo)
changed: [10.3.5.3] => (item=cloudera-cdh544.repo)
changed: [10.3.5.4] => (item=cloudera-cdh544.repo)
changed: [10.3.5.9] => (item=cloudera-cdh544.repo)
changed: [10.3.5.10] => (item=cloudera-gplextras544.repo)
changed: [10.3.4.160] => (item=cloudera-gplextras544.repo)
changed: [10.3.4.253] => (item=cloudera-gplextras544.repo)
changed: [10.3.5.11] => (item=cloudera-gplextras544.repo)
changed: [10.3.5.1] => (item=cloudera-gplextras544.repo)
changed: [10.3.5.5] => (item=cloudera-gplextras544.repo)
changed: [10.3.4.161] => (item=cloudera-gplextras544.repo)
changed: [10.3.5.2] => (item=cloudera-gplextras544.repo)
changed: [10.3.4.254] => (item=cloudera-gplextras544.repo)
changed: [10.3.5.7] => (item=cloudera-gplextras544.repo)
changed: [10.3.5.12] => (item=cloudera-gplextras544.repo)
changed: [10.3.5.4] => (item=cloudera-gplextras544.repo)
changed: [10.3.5.3] => (item=cloudera-gplextras544.repo)
changed: [10.3.5.9] => (item=cloudera-gplextras544.repo)

TASK: [create s3 key  bash file] ********************************************** 
changed: [10.3.4.160] => (item=add-s3keys-2-core-site)
changed: [10.3.4.254] => (item=add-s3keys-2-core-site)
changed: [10.3.5.4] => (item=add-s3keys-2-core-site)
changed: [10.3.4.161] => (item=add-s3keys-2-core-site)
changed: [10.3.5.7] => (item=add-s3keys-2-core-site)
changed: [10.3.4.253] => (item=add-s3keys-2-core-site)
changed: [10.3.5.10] => (item=add-s3keys-2-core-site)
changed: [10.3.5.5] => (item=add-s3keys-2-core-site)
changed: [10.3.5.2] => (item=add-s3keys-2-core-site)
changed: [10.3.5.1] => (item=add-s3keys-2-core-site)
changed: [10.3.5.12] => (item=add-s3keys-2-core-site)
changed: [10.3.5.11] => (item=add-s3keys-2-core-site)
changed: [10.3.5.3] => (item=add-s3keys-2-core-site)
changed: [10.3.5.9] => (item=add-s3keys-2-core-site)
changed: [10.3.4.160] => (item=jq)
changed: [10.3.5.4] => (item=jq)
changed: [10.3.4.161] => (item=jq)
changed: [10.3.4.254] => (item=jq)
changed: [10.3.5.7] => (item=jq)
changed: [10.3.4.253] => (item=jq)
changed: [10.3.5.2] => (item=jq)
changed: [10.3.5.11] => (item=jq)
changed: [10.3.5.10] => (item=jq)
changed: [10.3.5.5] => (item=jq)
changed: [10.3.5.1] => (item=jq)
changed: [10.3.5.9] => (item=jq)
changed: [10.3.5.12] => (item=jq)
changed: [10.3.5.3] => (item=jq)

TASK: [add cdh5 repo key] ***************************************************** 
changed: [10.3.4.160]
changed: [10.3.4.254]
changed: [10.3.4.161]
changed: [10.3.5.2]
changed: [10.3.5.10]
changed: [10.3.5.3]
changed: [10.3.5.5]
changed: [10.3.5.1]
changed: [10.3.4.253]
changed: [10.3.5.4]
changed: [10.3.5.12]
changed: [10.3.5.9]
changed: [10.3.5.7]
changed: [10.3.5.11]

TASK: [install needed rpms for hadoop] **************************************** 
changed: [10.3.4.253] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.5.9] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.5.4] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.5.2] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.5.11] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.5.10] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.4.254] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.5.7] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.5.1] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.5.3] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.5.12] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.5.5] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.4.160] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)
changed: [10.3.4.161] => (item=gcc,gcc-c++,make,java-1.7.0-openjdk.x86_64,java-1.7.0-openjdk-devel.x86_64,hadoop-lzo.x86_64,hadoop-lzo-native,3proxy-0.6.1-10.el6.x86_64)

TASK: [create the hosts file for all machines] ******************************** 
changed: [10.3.4.160]
changed: [10.3.4.253]
changed: [10.3.4.254]
changed: [10.3.5.10]
changed: [10.3.4.161]
changed: [10.3.5.1]
changed: [10.3.5.3]
changed: [10.3.5.11]
changed: [10.3.5.12]
changed: [10.3.5.4]
changed: [10.3.5.9]
changed: [10.3.5.5]
changed: [10.3.5.7]
changed: [10.3.5.2]

TASK: [install hadoop base pkgs] ********************************************** 
changed: [10.3.5.9] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.5.11] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.5.10] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.4.254] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.5.2] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.5.5] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.5.1] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.4.161] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.4.253] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.5.7] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.5.12] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.5.4] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.5.3] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)
changed: [10.3.4.160] => (item=hadoop,hadoop-mapreduce,hadoop-yarn,hadoop-hdfs)

TASK: [create all needed hadoop directories] ********************************** 
changed: [10.3.5.1] => (item=/var/hadoop)
changed: [10.3.4.253] => (item=/var/hadoop)
changed: [10.3.4.254] => (item=/var/hadoop)
changed: [10.3.5.10] => (item=/var/hadoop)
changed: [10.3.4.161] => (item=/var/hadoop)
changed: [10.3.4.160] => (item=/var/hadoop)
changed: [10.3.5.11] => (item=/var/hadoop)
changed: [10.3.5.12] => (item=/var/hadoop)
changed: [10.3.5.4] => (item=/var/hadoop)
changed: [10.3.5.2] => (item=/var/hadoop)
changed: [10.3.5.5] => (item=/var/hadoop)
changed: [10.3.5.9] => (item=/var/hadoop)
changed: [10.3.5.7] => (item=/var/hadoop)
changed: [10.3.5.3] => (item=/var/hadoop)
changed: [10.3.4.253] => (item=/var/hadoop/data)
changed: [10.3.5.1] => (item=/var/hadoop/data)
changed: [10.3.4.160] => (item=/var/hadoop/data)
changed: [10.3.4.254] => (item=/var/hadoop/data)
changed: [10.3.5.10] => (item=/var/hadoop/data)
changed: [10.3.5.4] => (item=/var/hadoop/data)
changed: [10.3.4.161] => (item=/var/hadoop/data)
changed: [10.3.5.12] => (item=/var/hadoop/data)
changed: [10.3.5.11] => (item=/var/hadoop/data)
changed: [10.3.5.3] => (item=/var/hadoop/data)
changed: [10.3.5.2] => (item=/var/hadoop/data)
changed: [10.3.5.9] => (item=/var/hadoop/data)
changed: [10.3.5.7] => (item=/var/hadoop/data)
changed: [10.3.5.5] => (item=/var/hadoop/data)
changed: [10.3.4.253] => (item=/var/hadoop/.status)
changed: [10.3.4.254] => (item=/var/hadoop/.status)
changed: [10.3.5.1] => (item=/var/hadoop/.status)
changed: [10.3.5.10] => (item=/var/hadoop/.status)
changed: [10.3.5.12] => (item=/var/hadoop/.status)
changed: [10.3.4.160] => (item=/var/hadoop/.status)
changed: [10.3.5.7] => (item=/var/hadoop/.status)
changed: [10.3.5.4] => (item=/var/hadoop/.status)
changed: [10.3.4.161] => (item=/var/hadoop/.status)
changed: [10.3.5.5] => (item=/var/hadoop/.status)
changed: [10.3.5.9] => (item=/var/hadoop/.status)
changed: [10.3.5.11] => (item=/var/hadoop/.status)
changed: [10.3.4.253] => (item=/root/deploy)
changed: [10.3.5.2] => (item=/var/hadoop/.status)
changed: [10.3.5.3] => (item=/var/hadoop/.status)
changed: [10.3.4.254] => (item=/root/deploy)
changed: [10.3.5.1] => (item=/root/deploy)
changed: [10.3.5.12] => (item=/root/deploy)
changed: [10.3.5.10] => (item=/root/deploy)
changed: [10.3.4.160] => (item=/root/deploy)
changed: [10.3.4.161] => (item=/root/deploy)
changed: [10.3.5.11] => (item=/root/deploy)
changed: [10.3.4.253] => (item=/root/deploy/hadoop)
changed: [10.3.5.9] => (item=/root/deploy)
changed: [10.3.5.7] => (item=/root/deploy)
changed: [10.3.5.4] => (item=/root/deploy)
changed: [10.3.5.5] => (item=/root/deploy)
changed: [10.3.5.2] => (item=/root/deploy)
changed: [10.3.5.3] => (item=/root/deploy)
changed: [10.3.5.12] => (item=/root/deploy/hadoop)
changed: [10.3.5.1] => (item=/root/deploy/hadoop)
changed: [10.3.5.10] => (item=/root/deploy/hadoop)
changed: [10.3.4.254] => (item=/root/deploy/hadoop)
changed: [10.3.4.160] => (item=/root/deploy/hadoop)
changed: [10.3.5.11] => (item=/root/deploy/hadoop)
changed: [10.3.4.161] => (item=/root/deploy/hadoop)
changed: [10.3.5.7] => (item=/root/deploy/hadoop)
changed: [10.3.5.9] => (item=/root/deploy/hadoop)
changed: [10.3.5.2] => (item=/root/deploy/hadoop)
changed: [10.3.5.4] => (item=/root/deploy/hadoop)
changed: [10.3.5.5] => (item=/root/deploy/hadoop)
changed: [10.3.5.3] => (item=/root/deploy/hadoop)

TASK: [install zookeeper base pkgs] ******************************************* 
ok: [10.3.5.1] => (item=zookeeper)
ok: [10.3.4.254] => (item=zookeeper)
ok: [10.3.5.10] => (item=zookeeper)
ok: [10.3.5.11] => (item=zookeeper)
ok: [10.3.4.253] => (item=zookeeper)
ok: [10.3.5.7] => (item=zookeeper)
ok: [10.3.5.3] => (item=zookeeper)
ok: [10.3.5.4] => (item=zookeeper)
ok: [10.3.5.2] => (item=zookeeper)
ok: [10.3.5.5] => (item=zookeeper)
ok: [10.3.5.9] => (item=zookeeper)
ok: [10.3.5.12] => (item=zookeeper)
ok: [10.3.4.161] => (item=zookeeper)
ok: [10.3.4.160] => (item=zookeeper)

TASK: [create zookeeper cfgs] ************************************************* 
changed: [10.3.4.253]
changed: [10.3.4.160]
changed: [10.3.4.254]
changed: [10.3.5.1]
changed: [10.3.4.161]
changed: [10.3.5.10]
changed: [10.3.5.9]
changed: [10.3.5.12]
changed: [10.3.5.11]
changed: [10.3.5.4]
changed: [10.3.5.2]
changed: [10.3.5.7]
changed: [10.3.5.3]
changed: [10.3.5.5]

TASK: [create /etc/hadoop/conf.{{nameservice_id}}] **************************** 
changed: [10.3.4.253]
changed: [10.3.4.161]
changed: [10.3.4.160]
changed: [10.3.4.254]
changed: [10.3.5.1]
changed: [10.3.5.10]
changed: [10.3.5.11]
changed: [10.3.5.4]
changed: [10.3.5.5]
changed: [10.3.5.12]
changed: [10.3.5.2]
changed: [10.3.5.9]
changed: [10.3.5.3]
changed: [10.3.5.7]

TASK: [create alternatives for hadoop-conf] *********************************** 
changed: [10.3.4.254] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.4.160] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.4.161] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.4.253] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.12] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.1] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.3] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.11] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.10] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.7] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.4] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.9] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.5] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.2] => (item=/etc/hadoop/conf.mycluster)

TASK: [create alternatives for hadoop-conf] *********************************** 
changed: [10.3.4.160] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.4.161] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.4.254] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.4.253] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.11] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.5] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.1] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.3] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.7] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.10] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.9] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.2] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.12] => (item=/etc/hadoop/conf.mycluster)
changed: [10.3.5.4] => (item=/etc/hadoop/conf.mycluster)

TASK: [copy the hadoop configuration files] *********************************** 
changed: [10.3.4.253] => (item=core-site.xml)
changed: [10.3.4.160] => (item=core-site.xml)
changed: [10.3.4.161] => (item=core-site.xml)
changed: [10.3.5.11] => (item=core-site.xml)
changed: [10.3.5.7] => (item=core-site.xml)
changed: [10.3.5.10] => (item=core-site.xml)
changed: [10.3.4.254] => (item=core-site.xml)
changed: [10.3.5.12] => (item=core-site.xml)
changed: [10.3.5.1] => (item=core-site.xml)
changed: [10.3.5.5] => (item=core-site.xml)
changed: [10.3.5.3] => (item=core-site.xml)
changed: [10.3.5.2] => (item=core-site.xml)
changed: [10.3.5.4] => (item=core-site.xml)
changed: [10.3.5.9] => (item=core-site.xml)
changed: [10.3.4.253] => (item=hdfs-site.xml)
changed: [10.3.4.160] => (item=hdfs-site.xml)
changed: [10.3.4.161] => (item=hdfs-site.xml)
changed: [10.3.5.11] => (item=hdfs-site.xml)
changed: [10.3.5.10] => (item=hdfs-site.xml)
changed: [10.3.5.7] => (item=hdfs-site.xml)
changed: [10.3.5.12] => (item=hdfs-site.xml)
changed: [10.3.4.254] => (item=hdfs-site.xml)
changed: [10.3.5.3] => (item=hdfs-site.xml)
changed: [10.3.5.9] => (item=hdfs-site.xml)
changed: [10.3.5.1] => (item=hdfs-site.xml)
changed: [10.3.5.2] => (item=hdfs-site.xml)
changed: [10.3.4.253] => (item=hadoop-env.sh)
changed: [10.3.5.4] => (item=hdfs-site.xml)
changed: [10.3.5.5] => (item=hdfs-site.xml)
changed: [10.3.4.160] => (item=hadoop-env.sh)
changed: [10.3.4.161] => (item=hadoop-env.sh)
changed: [10.3.5.11] => (item=hadoop-env.sh)
changed: [10.3.5.10] => (item=hadoop-env.sh)
changed: [10.3.5.7] => (item=hadoop-env.sh)
changed: [10.3.4.254] => (item=hadoop-env.sh)
changed: [10.3.5.2] => (item=hadoop-env.sh)
changed: [10.3.5.9] => (item=hadoop-env.sh)
changed: [10.3.5.12] => (item=hadoop-env.sh)
changed: [10.3.4.253] => (item=mapred-site.xml)
changed: [10.3.5.1] => (item=hadoop-env.sh)
changed: [10.3.5.3] => (item=hadoop-env.sh)
changed: [10.3.5.4] => (item=hadoop-env.sh)
changed: [10.3.5.5] => (item=hadoop-env.sh)
changed: [10.3.4.160] => (item=mapred-site.xml)
changed: [10.3.4.161] => (item=mapred-site.xml)
changed: [10.3.5.11] => (item=mapred-site.xml)
changed: [10.3.5.10] => (item=mapred-site.xml)
changed: [10.3.5.7] => (item=mapred-site.xml)
changed: [10.3.4.254] => (item=mapred-site.xml)
changed: [10.3.5.2] => (item=mapred-site.xml)
changed: [10.3.5.12] => (item=mapred-site.xml)
changed: [10.3.4.253] => (item=yarn-site.xml)
changed: [10.3.5.9] => (item=mapred-site.xml)
changed: [10.3.5.1] => (item=mapred-site.xml)
changed: [10.3.5.3] => (item=mapred-site.xml)
changed: [10.3.5.4] => (item=mapred-site.xml)
changed: [10.3.5.5] => (item=mapred-site.xml)
changed: [10.3.4.160] => (item=yarn-site.xml)
changed: [10.3.4.161] => (item=yarn-site.xml)
changed: [10.3.5.11] => (item=yarn-site.xml)
changed: [10.3.5.10] => (item=yarn-site.xml)
changed: [10.3.5.7] => (item=yarn-site.xml)
changed: [10.3.5.2] => (item=yarn-site.xml)
changed: [10.3.4.254] => (item=yarn-site.xml)
changed: [10.3.5.9] => (item=yarn-site.xml)
changed: [10.3.4.253] => (item=yarn-env.sh)
changed: [10.3.5.12] => (item=yarn-site.xml)
changed: [10.3.5.3] => (item=yarn-site.xml)
changed: [10.3.5.5] => (item=yarn-site.xml)
changed: [10.3.5.1] => (item=yarn-site.xml)
changed: [10.3.5.4] => (item=yarn-site.xml)
changed: [10.3.4.160] => (item=yarn-env.sh)
changed: [10.3.5.10] => (item=yarn-env.sh)
changed: [10.3.4.161] => (item=yarn-env.sh)
changed: [10.3.5.11] => (item=yarn-env.sh)
changed: [10.3.5.2] => (item=yarn-env.sh)
changed: [10.3.5.7] => (item=yarn-env.sh)
changed: [10.3.4.254] => (item=yarn-env.sh)
changed: [10.3.5.1] => (item=yarn-env.sh)
changed: [10.3.4.253] => (item=slaves)
changed: [10.3.5.12] => (item=yarn-env.sh)
changed: [10.3.5.3] => (item=yarn-env.sh)
changed: [10.3.5.5] => (item=yarn-env.sh)
changed: [10.3.5.9] => (item=yarn-env.sh)
changed: [10.3.5.4] => (item=yarn-env.sh)
changed: [10.3.4.160] => (item=slaves)
changed: [10.3.5.10] => (item=slaves)
changed: [10.3.5.11] => (item=slaves)
changed: [10.3.4.161] => (item=slaves)
changed: [10.3.5.2] => (item=slaves)
changed: [10.3.5.7] => (item=slaves)
changed: [10.3.4.254] => (item=slaves)
changed: [10.3.4.253] => (item=capacity-scheduler.xml)
changed: [10.3.5.1] => (item=slaves)
changed: [10.3.5.12] => (item=slaves)
changed: [10.3.5.9] => (item=slaves)
changed: [10.3.5.3] => (item=slaves)
changed: [10.3.5.4] => (item=slaves)
changed: [10.3.5.5] => (item=slaves)
changed: [10.3.5.11] => (item=capacity-scheduler.xml)
changed: [10.3.5.10] => (item=capacity-scheduler.xml)
changed: [10.3.4.160] => (item=capacity-scheduler.xml)
changed: [10.3.4.161] => (item=capacity-scheduler.xml)
changed: [10.3.5.2] => (item=capacity-scheduler.xml)
changed: [10.3.5.7] => (item=capacity-scheduler.xml)
changed: [10.3.4.254] => (item=capacity-scheduler.xml)
changed: [10.3.5.1] => (item=capacity-scheduler.xml)
changed: [10.3.4.253] => (item=configuration.xsl)
changed: [10.3.5.4] => (item=capacity-scheduler.xml)
changed: [10.3.5.3] => (item=capacity-scheduler.xml)
changed: [10.3.5.9] => (item=capacity-scheduler.xml)
changed: [10.3.5.12] => (item=capacity-scheduler.xml)
changed: [10.3.5.5] => (item=capacity-scheduler.xml)
changed: [10.3.5.11] => (item=configuration.xsl)
changed: [10.3.4.160] => (item=configuration.xsl)
changed: [10.3.5.10] => (item=configuration.xsl)
changed: [10.3.5.2] => (item=configuration.xsl)
changed: [10.3.4.161] => (item=configuration.xsl)
changed: [10.3.5.7] => (item=configuration.xsl)
changed: [10.3.4.254] => (item=configuration.xsl)
changed: [10.3.5.1] => (item=configuration.xsl)
changed: [10.3.4.253] => (item=container-executor.cfg)
changed: [10.3.5.3] => (item=configuration.xsl)
changed: [10.3.5.4] => (item=configuration.xsl)
changed: [10.3.5.9] => (item=configuration.xsl)
changed: [10.3.5.5] => (item=configuration.xsl)
changed: [10.3.5.12] => (item=configuration.xsl)
changed: [10.3.5.11] => (item=container-executor.cfg)
changed: [10.3.4.160] => (item=container-executor.cfg)
changed: [10.3.4.161] => (item=container-executor.cfg)
changed: [10.3.5.10] => (item=container-executor.cfg)
changed: [10.3.5.2] => (item=container-executor.cfg)
changed: [10.3.5.7] => (item=container-executor.cfg)
changed: [10.3.4.254] => (item=container-executor.cfg)
changed: [10.3.5.1] => (item=container-executor.cfg)
changed: [10.3.5.4] => (item=container-executor.cfg)
changed: [10.3.4.253] => (item=hadoop-metrics2.properties)
changed: [10.3.5.9] => (item=container-executor.cfg)
changed: [10.3.5.3] => (item=container-executor.cfg)
changed: [10.3.5.5] => (item=container-executor.cfg)
changed: [10.3.5.11] => (item=hadoop-metrics2.properties)
changed: [10.3.5.12] => (item=container-executor.cfg)
changed: [10.3.4.161] => (item=hadoop-metrics2.properties)
changed: [10.3.5.10] => (item=hadoop-metrics2.properties)
changed: [10.3.5.2] => (item=hadoop-metrics2.properties)
changed: [10.3.4.160] => (item=hadoop-metrics2.properties)
changed: [10.3.5.7] => (item=hadoop-metrics2.properties)
changed: [10.3.5.1] => (item=hadoop-metrics2.properties)
changed: [10.3.5.4] => (item=hadoop-metrics2.properties)
changed: [10.3.4.254] => (item=hadoop-metrics2.properties)
changed: [10.3.4.253] => (item=hadoop-metrics.properties)
changed: [10.3.5.9] => (item=hadoop-metrics2.properties)
changed: [10.3.5.3] => (item=hadoop-metrics2.properties)
changed: [10.3.5.12] => (item=hadoop-metrics2.properties)
changed: [10.3.5.11] => (item=hadoop-metrics.properties)
changed: [10.3.5.5] => (item=hadoop-metrics2.properties)
changed: [10.3.4.161] => (item=hadoop-metrics.properties)
changed: [10.3.5.2] => (item=hadoop-metrics.properties)
changed: [10.3.5.10] => (item=hadoop-metrics.properties)
changed: [10.3.5.1] => (item=hadoop-metrics.properties)
changed: [10.3.5.7] => (item=hadoop-metrics.properties)
changed: [10.3.4.160] => (item=hadoop-metrics.properties)
changed: [10.3.5.4] => (item=hadoop-metrics.properties)
changed: [10.3.4.254] => (item=hadoop-metrics.properties)
changed: [10.3.5.9] => (item=hadoop-metrics.properties)
changed: [10.3.4.253] => (item=hadoop-policy.xml)
changed: [10.3.5.3] => (item=hadoop-metrics.properties)
changed: [10.3.5.11] => (item=hadoop-policy.xml)
changed: [10.3.5.12] => (item=hadoop-metrics.properties)
changed: [10.3.5.5] => (item=hadoop-metrics.properties)
changed: [10.3.5.2] => (item=hadoop-policy.xml)
changed: [10.3.5.10] => (item=hadoop-policy.xml)
changed: [10.3.4.161] => (item=hadoop-policy.xml)
changed: [10.3.5.7] => (item=hadoop-policy.xml)
changed: [10.3.5.1] => (item=hadoop-policy.xml)
changed: [10.3.5.4] => (item=hadoop-policy.xml)
changed: [10.3.4.160] => (item=hadoop-policy.xml)
changed: [10.3.4.253] => (item=log4j.properties)
changed: [10.3.4.254] => (item=hadoop-policy.xml)
changed: [10.3.5.9] => (item=hadoop-policy.xml)
changed: [10.3.5.3] => (item=hadoop-policy.xml)
changed: [10.3.5.12] => (item=hadoop-policy.xml)
changed: [10.3.5.5] => (item=hadoop-policy.xml)
changed: [10.3.5.11] => (item=log4j.properties)
changed: [10.3.5.2] => (item=log4j.properties)
changed: [10.3.5.10] => (item=log4j.properties)
changed: [10.3.5.7] => (item=log4j.properties)
changed: [10.3.4.161] => (item=log4j.properties)
changed: [10.3.5.1] => (item=log4j.properties)
changed: [10.3.5.4] => (item=log4j.properties)
changed: [10.3.4.253] => (item=mapred-queues.xml.template)
changed: [10.3.4.160] => (item=log4j.properties)
changed: [10.3.4.254] => (item=log4j.properties)
changed: [10.3.5.9] => (item=log4j.properties)
changed: [10.3.5.5] => (item=log4j.properties)
changed: [10.3.5.11] => (item=mapred-queues.xml.template)
changed: [10.3.5.12] => (item=log4j.properties)
changed: [10.3.5.3] => (item=log4j.properties)
changed: [10.3.4.161] => (item=mapred-queues.xml.template)
changed: [10.3.5.2] => (item=mapred-queues.xml.template)
changed: [10.3.5.10] => (item=mapred-queues.xml.template)
changed: [10.3.5.7] => (item=mapred-queues.xml.template)
changed: [10.3.5.1] => (item=mapred-queues.xml.template)
changed: [10.3.5.4] => (item=mapred-queues.xml.template)
changed: [10.3.4.253] => (item=ssl-client.xml.example)
changed: [10.3.4.160] => (item=mapred-queues.xml.template)
changed: [10.3.4.254] => (item=mapred-queues.xml.template)
changed: [10.3.5.11] => (item=ssl-client.xml.example)
changed: [10.3.5.5] => (item=mapred-queues.xml.template)
changed: [10.3.5.3] => (item=mapred-queues.xml.template)
changed: [10.3.5.9] => (item=mapred-queues.xml.template)
changed: [10.3.5.12] => (item=mapred-queues.xml.template)
changed: [10.3.5.10] => (item=ssl-client.xml.example)
changed: [10.3.5.7] => (item=ssl-client.xml.example)
changed: [10.3.4.253] => (item=ssl-server.xml.example)
changed: [10.3.5.2] => (item=ssl-client.xml.example)
changed: [10.3.5.1] => (item=ssl-client.xml.example)
changed: [10.3.4.161] => (item=ssl-client.xml.example)
changed: [10.3.5.4] => (item=ssl-client.xml.example)
changed: [10.3.4.160] => (item=ssl-client.xml.example)
changed: [10.3.4.254] => (item=ssl-client.xml.example)
changed: [10.3.5.5] => (item=ssl-client.xml.example)
changed: [10.3.5.9] => (item=ssl-client.xml.example)
changed: [10.3.5.3] => (item=ssl-client.xml.example)
changed: [10.3.5.11] => (item=ssl-server.xml.example)
changed: [10.3.5.12] => (item=ssl-client.xml.example)
changed: [10.3.5.10] => (item=ssl-server.xml.example)
changed: [10.3.5.1] => (item=ssl-server.xml.example)
changed: [10.3.5.4] => (item=ssl-server.xml.example)
changed: [10.3.4.161] => (item=ssl-server.xml.example)
changed: [10.3.5.2] => (item=ssl-server.xml.example)
changed: [10.3.5.7] => (item=ssl-server.xml.example)
changed: [10.3.4.160] => (item=ssl-server.xml.example)
changed: [10.3.5.5] => (item=ssl-server.xml.example)
changed: [10.3.4.254] => (item=ssl-server.xml.example)
changed: [10.3.5.9] => (item=ssl-server.xml.example)
changed: [10.3.5.3] => (item=ssl-server.xml.example)
changed: [10.3.5.12] => (item=ssl-server.xml.example)

TASK: [create oozie group] **************************************************** 
changed: [10.3.4.253]
changed: [10.3.4.254]
changed: [10.3.4.161]
changed: [10.3.5.1]
changed: [10.3.4.160]
changed: [10.3.5.12]
changed: [10.3.5.2]
changed: [10.3.5.3]
changed: [10.3.5.11]
changed: [10.3.5.10]
changed: [10.3.5.5]
changed: [10.3.5.9]
changed: [10.3.5.4]
changed: [10.3.5.7]

TASK: [create oozie user] ***************************************************** 
changed: [10.3.4.160]
changed: [10.3.4.161]
changed: [10.3.4.254]
changed: [10.3.4.253]
changed: [10.3.5.1]
changed: [10.3.5.4]
changed: [10.3.5.11]
changed: [10.3.5.3]
changed: [10.3.5.10]
changed: [10.3.5.7]
changed: [10.3.5.9]
changed: [10.3.5.2]
changed: [10.3.5.5]
changed: [10.3.5.12]

TASK: [create .ssh directory for oozie user] ********************************** 
changed: [10.3.4.160]
changed: [10.3.5.1]
changed: [10.3.5.10]
changed: [10.3.4.254]
changed: [10.3.4.253]
changed: [10.3.4.161]
changed: [10.3.5.2]
changed: [10.3.5.11]
changed: [10.3.5.9]
changed: [10.3.5.12]
changed: [10.3.5.4]
changed: [10.3.5.3]
changed: [10.3.5.5]
changed: [10.3.5.7]

TASK: [copy the sshkeys for oozie user] *************************************** 
changed: [10.3.4.254] => (item=authorized_keys)
changed: [10.3.4.160] => (item=authorized_keys)
changed: [10.3.5.1] => (item=authorized_keys)
changed: [10.3.4.253] => (item=authorized_keys)
changed: [10.3.5.7] => (item=authorized_keys)
changed: [10.3.5.3] => (item=authorized_keys)
changed: [10.3.5.11] => (item=authorized_keys)
changed: [10.3.5.5] => (item=authorized_keys)
changed: [10.3.5.10] => (item=authorized_keys)
changed: [10.3.5.12] => (item=authorized_keys)
changed: [10.3.5.4] => (item=authorized_keys)
changed: [10.3.4.161] => (item=authorized_keys)
changed: [10.3.5.9] => (item=authorized_keys)
changed: [10.3.5.2] => (item=authorized_keys)
changed: [10.3.4.254] => (item=id_rsa)
changed: [10.3.4.160] => (item=id_rsa)
changed: [10.3.5.1] => (item=id_rsa)
changed: [10.3.4.253] => (item=id_rsa)
changed: [10.3.5.11] => (item=id_rsa)
changed: [10.3.5.9] => (item=id_rsa)
changed: [10.3.5.3] => (item=id_rsa)
changed: [10.3.5.7] => (item=id_rsa)
changed: [10.3.5.10] => (item=id_rsa)
changed: [10.3.4.161] => (item=id_rsa)
changed: [10.3.5.12] => (item=id_rsa)
changed: [10.3.5.2] => (item=id_rsa)
changed: [10.3.5.5] => (item=id_rsa)
changed: [10.3.5.4] => (item=id_rsa)
changed: [10.3.4.254] => (item=id_rsa.pub)
changed: [10.3.4.160] => (item=id_rsa.pub)
changed: [10.3.5.1] => (item=id_rsa.pub)
changed: [10.3.4.253] => (item=id_rsa.pub)
changed: [10.3.5.11] => (item=id_rsa.pub)
changed: [10.3.5.9] => (item=id_rsa.pub)
changed: [10.3.5.5] => (item=id_rsa.pub)
changed: [10.3.5.3] => (item=id_rsa.pub)
changed: [10.3.5.4] => (item=id_rsa.pub)
changed: [10.3.5.10] => (item=id_rsa.pub)
changed: [10.3.5.7] => (item=id_rsa.pub)
changed: [10.3.5.12] => (item=id_rsa.pub)
changed: [10.3.4.161] => (item=id_rsa.pub)
changed: [10.3.5.2] => (item=id_rsa.pub)

PLAY [cdh5-zookeeperserver] *************************************************** 

TASK: [install zookeeper server pkgs] ***************************************** 
changed: [10.3.5.10] => (item=zookeeper-server)
changed: [10.3.5.11] => (item=zookeeper-server)
changed: [10.3.5.12] => (item=zookeeper-server)

TASK: [create zookeeper_datadir] ********************************************** 
changed: [10.3.5.12]
changed: [10.3.5.11]
changed: [10.3.5.10]

TASK: [init zookeeper server] ************************************************* 
changed: [10.3.5.10]
changed: [10.3.5.11]
changed: [10.3.5.12]

TASK: [create zookeeper cfg] ************************************************** 
changed: [10.3.5.10]
changed: [10.3.5.11]
changed: [10.3.5.12]

TASK: [start zookeeper server] ************************************************ 
changed: [10.3.5.11]
changed: [10.3.5.12]
changed: [10.3.5.10]

NOTIFIED: [restart zookeeper server] ****************************************** 
changed: [10.3.5.10]
changed: [10.3.5.11]
changed: [10.3.5.12]

PLAY [cdh5-journalnode] ******************************************************* 

TASK: [install journalnode pkgs] ********************************************** 
changed: [10.3.5.10] => (item=hadoop-hdfs-journalnode)
changed: [10.3.5.11] => (item=hadoop-hdfs-journalnode)
changed: [10.3.5.12] => (item=hadoop-hdfs-journalnode)

TASK: [create folder for journaling] ****************************************** 
changed: [10.3.5.10]
changed: [10.3.5.11]
changed: [10.3.5.12]

TASK: [start journalnode services] ******************************************** 
changed: [10.3.5.10]
changed: [10.3.5.11]
changed: [10.3.5.12]

PLAY [cdh5-namenode-primary] ************************************************** 

TASK: [install namenode pkgs] ************************************************* 
changed: [10.3.4.160] => (item=hadoop-hdfs-namenode,hadoop-hdfs-zkfc)

TASK: [create the data directory for the namenode metadata] ******************* 
changed: [10.3.4.160] => (item=/var/hadoop/data/1/)
changed: [10.3.4.160] => (item=/var/hadoop/data/1/dfs/)
changed: [10.3.4.160] => (item=/var/hadoop/data/2/)
changed: [10.3.4.160] => (item=/var/hadoop/data/2/dfs/)
changed: [10.3.4.160] => (item=/var/hadoop/data/1/dfs/nn/)
changed: [10.3.4.160] => (item=/var/hadoop/data/2/dfs/nn)
changed: [10.3.4.160] => (item=['/data/hadoop/dfs/nn'])

TASK: [create the dfs hosts exclude file] ************************************* 
changed: [10.3.4.160]

TASK: [format the namenode] *************************************************** 
changed: [10.3.4.160] => (item=/var/hadoop/.status/namenode.formatted)

TASK: [start hadoop namenode services] **************************************** 
changed: [10.3.4.160] => (item=hadoop-hdfs-namenode)

PLAY [cdh5-namenode-backup] *************************************************** 

TASK: [install namenode pkgs] ************************************************* 
changed: [10.3.4.161] => (item=hadoop-hdfs-namenode,hadoop-hdfs-zkfc)

TASK: [create the data directory for the namenode metadata] ******************* 
changed: [10.3.4.161] => (item=['/data/hadoop/dfs/nn'])

TASK: [create the dfs hosts exclude file] ************************************* 
changed: [10.3.4.161]

TASK: [initialize the backup namenode] **************************************** 
changed: [10.3.4.161] => (item=/var/hadoop/.status/namenode.formatted)

TASK: [start hadoop namenode services] **************************************** 
changed: [10.3.4.161] => (item=hadoop-hdfs-namenode)

TASK: [initialize the zkfc for namenode] ************************************** 
changed: [10.3.4.161] => (item=/var/hadoop/.status/zkfc.formatted)

TASK: [start zkfc for namenodes] ********************************************** 
changed: [10.3.4.161]

PLAY [cdh5-namenode-primary] ************************************************** 

TASK: [start zkfc for namenodes] ********************************************** 
changed: [10.3.4.160]

PLAY [cdh5-httpfs] ************************************************************ 

TASK: [installl httpfs pkgs] ************************************************** 
changed: [10.3.4.161] => (item=hadoop-httpfs)
changed: [10.3.4.160] => (item=hadoop-httpfs)

TASK: [start httpfs service] ************************************************** 
changed: [10.3.4.161]
changed: [10.3.4.160]

PLAY [cdh5-slave] ************************************************************* 

TASK: [install datanode nodemanager and mapreduce pkgs] *********************** 
changed: [10.3.5.1] => (item=hadoop-yarn-nodemanager,hadoop-hdfs-datanode,hadoop-mapreduce)
changed: [10.3.5.4] => (item=hadoop-yarn-nodemanager,hadoop-hdfs-datanode,hadoop-mapreduce)
changed: [10.3.4.254] => (item=hadoop-yarn-nodemanager,hadoop-hdfs-datanode,hadoop-mapreduce)
changed: [10.3.5.7] => (item=hadoop-yarn-nodemanager,hadoop-hdfs-datanode,hadoop-mapreduce)
changed: [10.3.5.9] => (item=hadoop-yarn-nodemanager,hadoop-hdfs-datanode,hadoop-mapreduce)
changed: [10.3.5.5] => (item=hadoop-yarn-nodemanager,hadoop-hdfs-datanode,hadoop-mapreduce)
changed: [10.3.5.3] => (item=hadoop-yarn-nodemanager,hadoop-hdfs-datanode,hadoop-mapreduce)
changed: [10.3.5.2] => (item=hadoop-yarn-nodemanager,hadoop-hdfs-datanode,hadoop-mapreduce)
