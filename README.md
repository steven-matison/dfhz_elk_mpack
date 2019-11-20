# dfhz_elk_mpack
<h1>DFHeinz ELK Stack Management Pack for Ambari.</h1>

Install Elasticsearch, Logstash, Kibana, FileBeat, & MetricBeat with Ambari using this management pack created by DFHeinz.

<h2>Version Key</h2>

&nbsp;&nbsp;elasticsearch_mpack-3.4.0.1-0.tar.gz - HDP/HDF 3.4 Ambari 2.7 Mpack ELK 7.4 without sudo - WORK IN PROGRESS

&nbsp;&nbsp;elasticsearch_mpack-3.4.0.0-0.tar.gz - HDP/HDF 3.4 Ambari 2.7 Mpack ELK 6.3.2 without sudo 

&nbsp;&nbsp;elasticsearch_mpack-3.0.0.0-1.tar.gz - HDP/HDF 3.3 Ambari 2.7 Mpack ELK 6.3.2 with sudo (for non root user installl) 

&nbsp;&nbsp;elasticsearch_mpack-3.0.0.0-0.tar.gz - HDP/HDF 3.3 Ambari 2.7 Mpack ELK 6.3.2 without sudo 

&nbsp;&nbsp;elasticsearch_mpack-2.6.0.0-9.tar.gz - HDP/HDF 2 Ambari 2.6 Mpack ELK 6.3.2 with sudo

For more information about lifecycle of this Management Pack for Elasticsearch and how to install Elasticsearch using Ambari  please see the following Hortonworks Articles:

https://community.cloudera.com/t5/Community-Articles/How-To-Install-ELK-Stack-6-3-2-in-Ambari/ta-p/248842
https://community.cloudera.com/t5/Community-Articles/Improve-ELK-Mpack-for-HDP-HDF-3-for-Ambari-2-7/ta-p/249473

<h2>M-Pack Usage Notes</h2>

Make sure you get the correct /raw/ link if using the github links (see sample below).  
Be sure to restart ambari after all M-Pack changes.

Example  Install & Remove commands are:

<pre>ambari-server install-mpack --mpack=https://github.com/steven-dfheinz/dfhz_elk_mpack/raw/master/elasticsearch_mpack-3.4.0.0-0.tar.gz --verbose
ambari-server restart
ambari-server uninstall-mpack --mpack-name=elasticsearch-ambari.mpack
ambari-server restart</pre>

There is a current bug in User Group Management.  The work around is the following python command:
<pre>python /var/lib/ambari-server/resources/scripts/configs.py -u admin -p admin -n [CLUSTER_NAME] -l [CLUSTER_FQDN] -t 8080 -a set -c cluster-env -k  ignore_groupsusers_create -v true</pre>

