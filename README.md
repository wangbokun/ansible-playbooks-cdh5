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


