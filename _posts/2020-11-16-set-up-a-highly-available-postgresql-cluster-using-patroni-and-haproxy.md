---
id: 3106
title: 'How to Set Up a Highly Available PostgreSQL Cluster Using Patroni and HAProxy on Ubuntu?'
date: '2020-11-16T17:22:39+05:30'
author: 'Vikram Aruchamy'
layout: post
guid: 'http://149.28.53.131/?p=3106'
permalink: /set-up-a-highly-available-postgresql-cluster-using-patroni-and-haproxy/
rank_math_seo_score:
    - '68'
rank_math_internal_links_processed:
    - '1'
rank_math_primary_category:
    - '16'
rank_math_focus_keyword:
    - 'How to Set Up a Highly Available PostgreSQL Cluster Using Patroni and HAProxy,postgresql'
rank_math_pillar_content:
    - 'on'
rank_math_description:
    - 'In this tutorial, You''ll set up a highly available Postgresql cluster using Patroni and HAProxy on Ubuntu. '
ss_ss_share_count_facebook:
    - '13'
socialsnap_share_count_timestamp:
    - '2023-09-15 18:28:39'
ss_total_share_count:
    - '13'
ss_ss_click_share_count_facebook:
    - '1'
ss_social_share_disable:
    - '0'
bialty_cs_alt:
    - ''
tcb2_ready:
    - '1'
ss_ss_click_share_count_linkedin:
    - '1'
tap_disable_autolinker:
    - 'no'
tap_autolink_inside_heading:
    - global
tap_autolink_random_placement:
    - global
tap_post_autolinker_limit:
    - '0'
tve_landing_page:
    - ''
tve_disable_theme_dependency:
    - ''
tve_content_before_more:
    - ''
tve_content_more_found:
    - ''
tve_save_post:
    - ''
tve_custom_css:
    - ''
tve_user_custom_css:
    - ''
tve_page_events:
    - ''
tve_globals:
    - ''
tve_global_scripts:
    - ''
thrive_icon_pack:
    - ''
thrive_tcb_post_fonts:
    - ''
tve_has_masonry:
    - ''
tve_has_typefocus:
    - ''
tve_updated_post:
    - ''
tve_has_wistia_popover:
    - ''
rank_math_analytic_object_id:
    - '29'
image: /wp-content/uploads/2020/11/highly-available-postgresql-cluster-using-Patroni-and-HAProxy.png
categories:
    - how-to
tags:
    - aws
    - 'high availability'
    - postgresql
---

## <span class="ez-toc-section" id="introduction"></span>**Introduction**<span class="ez-toc-section-end"></span>

PostgreSQL is an opensource relational database that can run on major operating systems. It is highly robust and versatile, but doesn’t have features for the [high availability](https://en.wikipedia.org/wiki/High_availability). There are other open source frameworks available which can be used to manage high availability of the PostgreSQL Database.

In this tutorial, you’ll set up the PostgreSQL with high availability using Patroni, ETCD and HAProxy.

**Patroni is a template for you to create your own customized, high-availability solution developed using Python**. It is also capable of handling Database replication, backup and restoration configurations.

**ETCD is a fault-tolerant, distributed key-value store that is used to store the state of the PostgreSQL cluster. It gracefully handles leader elections during network partitions and can tolerate machine failure, even in the leader node.**

Whenever there is a change in the state of any PostgreSQL node in the cluster, Patroni updates the state change in the ETCD key-value store. With this information, ETCD elects the master node and keeps the cluster UP and running.

With this high availability solution which has more than one database instances in a single cluster, the master node of the cluster keeps changing in case of any failure. It becomes difficult to maintain the database end points in this situation. To solve this, **[HAProxy ](https://en.wikipedia.org/wiki/HAProxy)can be used. It keeps track of changes in the Master/Slave nodes and connects to the appropriate master node when the clients request connection**.

When you’re finished, you will have a robust and highly available PostgreSQL cluster ready for production use.

## <span class="ez-toc-section" id="prerequisites"></span>**Prerequisites**<span class="ez-toc-section-end"></span>

Before you begin this guide, you’ll need the following:

- Create 5 EC2 instances in AWS by following the guide [How to launch EC2 instance in EC2](http://149.28.53.131/how-to-launch-ec2-instance-in-aws-step-by-step/).
- In all five nodes, Update the packages list which are upgrade-able using <mark>*sudo apt update*</mark>
- In all five nodes, Upgrade the packages to the latest versions using <mark>*sudo apt upgrade*</mark>
- Install PostgreSQL on three of your servers by following the [Install PostgreSQL on Ubuntu 20.04](http://149.28.53.131/install-postgresql-on-ubuntu/). Just follow Step 1 of PostgreSQL installation tutorial. **Other steps should be ignored**. These three servers are referred as **node-1, node-2, node-3** in this tutorial.
- Ensure Python 3 is available on your three servers where PostgreSQL is installed by following the guide [Install python](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/eb-cli3-install-linux.html).
- Ensure Pip3 package manager is installed on all your servers to install and manage packages on your servers by following the guide [How to Install Pip3 on Ubuntu 20.04 and Use It?](http://149.28.53.131/install-pip3-on-ubuntu/)
- Reserve two servers for installing *etcd* and *HAProxy*. We will refer to these servers as **node-4 and node-5** respectively.

## <span class="ez-toc-section" id="step_1_%e2%80%94_configuring_your_node_firewalls"></span>**Step 1 — Configuring Your Node Firewalls**<span class="ez-toc-section-end"></span>

You need to configure [security groups](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/security-group-rules-reference.html) of your servers to restrict the Incoming and the Outgoing traffic to the EC2 Instances.

You can learn How to create a security groups, edit the security groups in [this working with security groups guide.](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/working-with-security-groups.html#creating-security-group)

Now, let’s see how to configure the security groups for your nodes.

### **Configuring Ports for Postgresql**

Create a rule to allow inbound traffic from the nodes(**node-1, node-2, node-3,node-5**) via port 8008.

- Patroni’s REST API uses port 8008 to provide the health checks and cluster messaging between the participating nodes.

Create a rule to allow inbound traffic from the nodes(**node-1, node-2, node-3, node-5** ) via port 5432.

- Postgresql listens to port 5432 for the database transactions and and Data Replication.

Apply the security group to the PostgreSQL nodes(**node-1, node-2, node-3**).

- This allows PostgreSQL nodes to communicate between each other for creating replicas.

Apply the security group to the HAProxy node(**node-5**).

- This allows HAProxy node to communicate with the active Master postgresql node in the cluster.

### **Configuring Ports for ETCD**

Create a rule to allow inbound traffic from the nodes (**node-1, node-2, node-3**) via port 2379.

- ETCD uses the port 2379 for the client requests. Clients communicate with ETCD using this port to read and write information from ETCD. *For e.g. Database connection details, current leader node information, node status etc.*

Apply the security group to the ETCD node(**node-4**).

- This allows ETCD node to communicate with the Postgres client node in the cluster.

### **Configuring Ports for HAProxy**

Create a rule to allow inbound traffic from all IPV4 and IPV6 address via port 7000.

- HAproxy uses the port 7000 to serve the client requests for the database transactions. If you already know your client IP Address, then you can use only that IP address in the source. This will ensure **only** the traffic from your client is served by HAProxy and other requests are dropped.

Apply the security group to the HAProxy node(**node-5**).

- This allows HAproxy node to serve the requests for the database transaction.

The firewall configuration is complete for the Highly available postresql cluster. You can now move on and start setting up the cluster.

## <span class="ez-toc-section" id="step_2_%e2%80%94_stopping_postgres_service"></span>**Step 2 — Stopping Postgres Service**<span class="ez-toc-section-end"></span>

When PostgreSQL in installed, it automatically starts as a system service. You should stop this PostgreSQL service so that Patroni can take care of running the PostgreSQL Service.

The `systemctl` command is used to manage the *systemd* services. Use stop with systemctl to stop the system service.

Execute the following command to stop the PostgreSQL service.

```
<pre class="wp-block-code command">```
sudo systemctl stop postgresql
```
```

Note: You should execute this command in all three servers(**node-1, node-2, node-3**)where PostgreSQL is installed.

Now the PostgreSQL service is stopped in all nodes(**node-1, node-2, node-3**).

You can now install Patroni, so that it takes charge of running PostgreSQL Service as required.

## <span class="ez-toc-section" id="step_3_%e2%80%94_installing_patroni"></span>**Step 3 — Installing Patroni**<span class="ez-toc-section-end"></span>

In this step, you’ll install Patroni with PIP3 the python package manager.

During Installation, Patroni uses utilities that come installed with postgres, located in the `<mark>/usr/lib/postgresql/12/bin</mark>` directory by default.

Hence you need to create symbolic links in the PATH to ensure that Patroni can find the utilities during the installation. <mark>ln</mark> command with <mark>-s</mark> option is used to create symbolic links.

Execute the below command to create the symbolic link.

```
<pre class="wp-block-code">```
sudo ln -s /usr/lib/postgresql/12/bin/* /usr/sbin/
```
```

Make sure you replace postgresql version according to the version installed.

The <mark>pip3 install</mark> command is used to [install additional Python packages](http://149.28.53.131/install-pip3-on-ubuntu/).

Execute the following command to install Patroni along with its dependencies psycopg2-binary and python-etcd.

```
<pre class="wp-block-code">```
sudo pip3 install patroni psycopg2-binary python-etcd
```
```

Note: You should execute this command in all three servers(**node-1, node-2, node-3**) where PostgreSQL is installed, so that the PostgreSQL configuration can be handled using Patroni.

Now, you can install the etcd to handle the distributed cluster.

## <span class="ez-toc-section" id="step_4_%e2%80%94_installing_etcd"></span>**Step 4 — Installing Etcd**<span class="ez-toc-section-end"></span>

In this step, you will install ETCD using the apt-get install command.

The <mark>apt install</mark> command is used to install packages with all the necessary dependencies.

Execute the following command to install etcd in the **node-4** reserved for etcd.

```
<pre class="wp-block-code">```
sudo apt install etcd
```
```

etcd is installed successfully. Now, you can install HAProxy that provides high availability.

## <span class="ez-toc-section" id="step_5_%e2%80%94_installing_haproxy"></span>**Step 5 — Installing HAProxy**<span class="ez-toc-section-end"></span>

HAProxy is free, open source software that provides a high availability load balancer and proxy server for TCP and HTTP-based applications that spreads requests across multiple servers.

The <mark>apt install</mark> command is used to install packages with all the necessary dependencies.

Execute the following command to install HAProxy in the **node-5** reserved for HAProxy:

```
<pre class="wp-block-code">```
sudo apt install haproxy
```
```

HAProxy is installed successfully.

Now all the installations are complete in the relevant servers and you’ll start the configuration of etcd, Patroni and HAProxy.

## <span class="ez-toc-section" id="step_6_%e2%80%94_configuring_etcd"></span>**Step 6 — Configuring Etcd**<span class="ez-toc-section-end"></span>

etcd is a fault-tolerant, distributed key-value store that is used to store the state of the postgres cluster. It gracefully handles leader elections in the cluster and can tolerate machine failure, even in the leader node.

You’ve installed etcd in the step3.

Now, you will configure etcd to handle the leader elections in the highly available cluster and store the state of the postgres cluster.

Using Patroni, all of the postgres nodes makes use of etcd to keep the postgres cluster up and running.

During the installation of the etcd, a default etcd configuration file is created in the location *<mark>/etc/default/etcd</mark>*.

nano tool is used edit the file. Use sudo nano to open the file in the edit mode. If you do not use sudo, nano will open the file in the read only mode.

Execute the below command to open and update the configuration file.

```
<pre class="wp-block-code">```
sudo nano /etc/default/etcd
```
```

nano opens the file.

Now the etcd default configuration file is opened where all the parameters are commented. Look for the each of the below parameters, uncomment it and update the settings with the relevant etcd server IP address as give below.

/etcd/default/etcd

```
<pre class="wp-block-code config">```
ETCD_LISTEN_PEER_URLS="http://<span style="background-color: rgba(242,201,76,.35)">node-4-server-ip</span>:2380"
ETCD_LISTEN_CLIENT_URLS="http://localhost:2379,http://<span style="background-color: rgba(242,201,76,.35)">node-4-server-ip</span>:2379"
ETCD_INITIAL_ADVERTISE_PEER_URLS="http://<span style="background-color: rgba(242,201,76,.35)">node-4-server-ip</span>:2380"
ETCD_INITIAL_CLUSTER="default=http://<span style="background-color: rgba(242,201,76,.35)">node-4-server-ip</span>:2380,"
ETCD_ADVERTISE_CLIENT_URLS="http://<span style="background-color: rgba(242,201,76,.35)">node-4-server-ip</span>:2379"
ETCD_INITIAL_CLUSTER_TOKEN="etcd-cluster"
ETCD_INITIAL_CLUSTER_STATE="new" 
``` 
```

Save the changes to the file and exit the nano editor.

You can learn more about etcd configuration parameters in the [official etcd page](https://etcd.io/docs/v3.4.0/op-guide/configuration/). Here’s what each line in this file is for:

- **ETCD LISTEN PEER URLS** – This flag informs the etcd to accept incoming requests from its peers on the specified scheme://IP:port combinations.
- **ETCD LISTEN CLIENT URLS** – This flag informs the etcd to accept incoming requests from the clients on the specified scheme://IP:port combinations.
- **ETCD INITIAL ADVERTISE PEER URLS** – This flag specifies the list of this member’s peer URLs to advertise to the rest of the cluster. These addresses are used for communicating etcd data around the cluster.  
    At least one must be routable to all cluster members. These URLs can contain domain names as well.
- **ETCD INITIAL CLUSTER** – This is the initial cluster configuration for bootstrapping. The key is the value of the –name flag for each node provided.
- **ETCD ADVERTISE CLIENT URLS** – This flag specifies the list of this member’s client URLs to advertise to the rest of the cluster. These URLs can contain domain names as well.
- **ETCD INITIAL CLUSTER TOKEN** – This flag specifies the Initial cluster token for the etcd cluster during bootstrap. Default token name is “etcd-cluster”.
- **ETCD INITIAL CLUSTER STATE** – This flag is used to denote the Initial cluster state (“new” or “existing”). Set to new for all members present during initial static or DNS bootstrapping.

Now, you need to restart etcd for the configuration changes to be effective.

The <mark>systemctl </mark>command is used to manage the *systemd* services. Use restart with systemctl to restart the system service.

Execute the following command to restart the etcd service.

```
<pre class="wp-block-code">```
sudo systemctl restart etcd
```
```

Now etcd is running with the updated configurations.

Use enable with <mark>systemctl</mark> to enable automatic start of etcd service after every system reboot.

Execute the following command to enable automatic start of etcd service after system reboot.

```
<pre class="wp-block-code">```
sudo systemctl enable etcd
```
```

You can use status with the systemctl to check the status of the system service.

Execute the following command to check the status of the etcd service.

```
<pre class="wp-block-code">```
sudo systemctl status etcd
```
```

You will see the below messages if the etcd configuration is successful.

```
<pre class="wp-block-code config">```
etcd.service - etcd - highly-available key value store
     Loaded: loaded (/lib/systemd/system/etcd.service; enabled; vendor preset: enabled)
     Active: active (running) since Thu 2020-08-27 14:03:57 UTC; 11h ago
       Docs: https://github.com/coreos/etcd
             man:etcd
   Main PID: 14786 (etcd)
      Tasks: 9 (limit: 1137)
     Memory: 61.2M
     CGroup: /system.slice/etcd.service
             └─14786 /usr/bin/etcd
Aug 27 14:03:57 do-04 etcd[14786]: 8e9e05c52164694d received MsgVoteResp from 8e9e05c52164694d at term 3
Aug 27 14:03:57 do-04 etcd[14786]: 8e9e05c52164694d became leader at term 3
Aug 27 14:03:57 do-04 etcd[14786]: raft.node: 8e9e05c52164694d elected leader 8e9e05c52164694d at term 3
Aug 27 14:03:57 do-04 etcd[14786]: published {Name:do-04 ClientURLs:[http://157.245.111.222:2379]} to cluster cdf818194e3a8c32
Aug 27 14:03:57 do-04 systemd[1]: Started etcd - highly-available key value store.
Aug 27 14:03:57 do-04 etcd[14786]: ready to serve client requests
Aug 27 16:59:14 do-04 etcd[14786]: sync duration of 1.165829808s, expected less than 1s
```
```

You’ve configured ETCD to maintain the state of the PostgreSQL nodes. Next, you’ll configure Patroni which can update the state of the PostgreSQL nodes to the ETCD key-value store.

## <span class="ez-toc-section" id="step_7_%e2%80%94_configuring_patroni"></span>**Step 7 — Configuring Patroni**<span class="ez-toc-section-end"></span>

Patroni is a Python package used to handle PostgreSQL configuration in the high availability clusters. You’ve already installed Patroni in the Step 3 in node-1, node-2, node-3.

Now, you will configure Patroni *using a YAML file* in the *<mark>/etc/patroni/</mark>* directory to handle the PostgreSQL service in node-1. A default YAML file is available in the offical Patroni GitHub [URL](https://github.com/zalando/patroni/blob/master/postgres0.yml).

Create a directory patroni inside the /etc/ folder using the mkdir command as below.

```
<pre class="wp-block-preformatted">sudo mkdir /etc/patroni
```

You should navigate to the <mark>/etc/patroni/</mark> directory to copy the YAML file to that location. <mark>cd</mark> command can be used to navigate to the specified directory.

Execute the following command to navigate to the *<mark>/etc/patroni/</mark>* directory.

```
<pre class="wp-block-preformatted">cd /etc/patroni/
```

Now, your current working directory is <mark>/etc/patroni/</mark>.

Next, you need to copy the raw [default YAML](https://raw.githubusercontent.com/zalando/patroni/master/postgres0.yml) file from GitHub to the <mark>/etc/patroni/</mark> directory.

curl tool is used to copy data from a server to another server.

Execute the below command to copy the YAML file from GitHub to your server.

```
<pre class="wp-block-preformatted">sudo curl -o config.yml https://raw.githubusercontent.com/zalando/patroni/master/postgres0.yml
```

The <mark>-o</mark> option in the <mark>curl</mark> command copies the file with the filename specified in the command. Here it creates a file named config.yml.

Now, you need to update the config.yml file with the right configuration.

Execute the below command to open and update the configuration file.

```
<pre class="wp-block-preformatted">sudo nano config.yml
```

Update the highlighted parameters in the config.yml.

/etc/patroni/config.yml

```
<pre class="wp-block-code  config">```
scope: postgres
namespace: <span style="background-color: rgba(242,201,76,.35)">/db/</span>
name: <span style="background-color: rgba(242,201,76,.35)">node1</span>

restapi:
  listen: <span style="background-color: rgba(242,201,76,.35)">node-1-server-ip</span>:8008
  connect_address: <span style="background-color: rgba(242,201,76,.35)">node-1-server-ip</span>:8008
#  Certfile: /etc/ssl/certs/ssl-Cert-snakeoil.pem
#  Keyfile: /etc/ssl/private/ssl-Cert-snakeoil.key
#  Authentication:
#    Username: Username
#    Password: Password

# Ctl:
#   Insecure: False # Allow Connections to SSL Sites Without Certs
#   Certfile: /etc/ssl/certs/ssl-Cert-snakeoil.pem
#   Cacert: /etc/ssl/certs/ssl-Cacert-snakeoil.pem

etcd:
  #Provide host to do the initial discovery of the cluster topology:
  host: <span style="background-color: rgba(242,201,76,.35)">node-4-server-ip</span>:2379
  #Or use "hosts" to provide multiple endpoints
  #Could be a comma separated string:
  #hosts: host1:port1,host2:port2
  #or an actual yaml list:
  #hosts:
  #- host1:port1
  #- host2:port2
  #Once discovery is complete Patroni will use the list of advertised clientURLs
  #It is possible to change this behavior through by setting:
  #use_proxies: true

#Raft:
#  data_dir: .
#  self_addr: 127.0.0.1:2222
#  partner_addrs:
#  - 127.0.0.1:2223
#  - 127.0.0.1:2224

bootstrap:
  # this section will be written into Etcd:/<namespace>/<scope>/config after initializing new cluster
  # and all other cluster members will use it as a `global configuration`
  dcs:
    ttl: 30
    loop_wait: 10
    retry_timeout: 10
    maximum_lag_on_failover: 1048576
#    master_start_timeout: 300
#    synchronous_mode: False
    #standby_cluster:
      #host: 127.0.0.1
      #port: 1111
      #primary_slot_name: patroni
    postgresql:
      use_pg_rewind: true
#      use_slots: True
      parameters:
#        wal_level: hot_standby
#        hot_standby: "on"
#        wal_keep_segments: 8
#        max_wal_senders: 10
#        max_replication_slots: 10
#        wal_log_hints: "on"
#        archive_mode: "on"
#        archive_timeout: 1800s
#        archive_command: Mkdir -P ../wal_archive && Test ! -F ../wal_archive/%F && Cp %P ../wal_archive/%F
#      recovery_conf:
#        restore_command: Cp ../wal_archive/%F %P

  # some desired options for 'initdb'
  initdb:  # Note: It needs to be a list (some options need values, others are switches)
  - encoding: UTF8
  - data-checksums

  pg_hba:  # Add following lines to pg_hba.conf after running 'initdb'
  # For kerberos gss based connectivity (discard @.*$)
  #- host replication replicator 127.0.0.1/32 gss include_realm=0
  #- host all all 0.0.0.0/0 gss include_realm=0
  - <span style="background-color: rgba(242,201,76,.35)">host replication replicator 127.0.0.1/32 md5</span>
  - <span style="background-color: rgba(242,201,76,.35)">host replication replicator node-1-server-ip/0 md5</span>
  - <span style="background-color: rgba(242,201,76,.35)">host replication replicator node-2-server-ip/0 md5</span>
  - <span style="background-color: rgba(242,201,76,.35)">host replication replicator node-3-server-ip/0 md5</span>
  - <span style="background-color: rgba(242,201,76,.35)">host all all 0.0.0.0/0 md5</span>
#  - Hostssl All All 0.0.0.0/0 Md5

  # Additional script to be launched after initial cluster creation (will be passed the connection URL as parameter)
# post_init: /usr/local/bin/setup_cluster.sh

  # Some additional users users which needs to be created after initializing new cluster
  users:
    admin:
      password: admin
      options:
        - createrole
        - createdb

postgresql:
  listen: <span style="background-color: rgba(242,201,76,.35)">node-1-server-ip:5432</span>
  connect_address: <span style="background-color: rgba(242,201,76,.35)">node-1-server-ip:5432</span>
  data_dir: <span style="background-color: rgba(242,201,76,.35)">/data/patroni</span>
#  bin_dir:
#  config_dir:
  pgpass: /tmp/pgpass0
  authentication:
    replication:
      username: replicator
      password: <span style="background-color: rgba(242,201,76,.35)">rep-pass</span>
    superuser:
      username: postgres
      password: <span style="background-color: rgba(242,201,76,.35)">zalando</span>
    rewind:  # Has no effect on postgres 10 and lower
      username: rewind_user
      password: rewind_password
  # Server side kerberos spn
#  Krbsrvname: Postgres
  parameters:
    # Fully qualified kerberos ticket file for the running user
    # same as KRB5CCNAME used by the GSS
#   krb_server_keyfile: /var/spool/keytabs/postgres
    unix_socket_directories: '.'

#Watchdog:
#  Mode: Automatic # Allowed Values: Off, Automatic, Required
#  Device: /dev/watchdog
#  safety_margin: 5

tags:
    nofailover: false
    noloadbalance: false
    clonefrom: false
    nosync: false </scope></namespace>
``` 
```

You can learn more about Patroni configuration parameters in the [official patroni docs page](https://patroni.readthedocs.io/en/latest/SETTINGS.html). Here’s what each line in this file is for in the different sections of the file.

**Global section:**

- scope – Name for the highly available postgres cluster
- namespace -path within the configuration store where Patroni will keep information about the cluster. Default value: “/service”.
- name – the name of the host. Must be unique for the cluster. for e.g. (node-1 in the first server, node-2 in the second server and so on).

**RestAPI section:**

- listen – IP address (or hostname) and port that Patroni will listen to for the REST API – to provide also the same health checks and cluster messaging between the participating nodes.
- connect\_address – IP address (or hostname) and port, to access the Patroni’s [REST API](https://patroni.readthedocs.io/en/latest/rest_api.html#rest-api).

**etcd section:**

- host – information for the etcd endpoint for the clusters.

**Bootstrap configuration section:**

- pg\_hba – list of lines that you should add to pg\_hba.conf. Client authentication is controlled by this pg\_hba.conf file. You can read more about this file in the [official postgresql page](https://www.postgresql.org/docs/9.1/auth-pg-hba-conf.html).  
    You will add the lines of the three nodes which can be used for authentication during the replication between the servers.

**postgresql section:**

- listen – IP address + port that Postgres listens to. It must be accessible from other nodes in the cluster.
- connect\_address – IP address + port through which Postgres is accessible from other nodes and applications.
- data\_dir – The location of the Postgres data directory, either [existing](https://patroni.readthedocs.io/en/latest/existing_data.html#existing-data) or to be initialized by Patroni.
- authentication – Authentication section has the username and passwords specified for the superuser, replication user.  
    SuperUser is a user which has no access restrictions in the Postgresql database. Superuser is used by Patroni to connect to the postgresql database.  
    Replication user is a user which has permissions to perform the replication between the master and slave nodes and used by replicas to access master via streaming replication.  
    You can specify the passwords for the superuser and replication user in the password properties of the users respectively. Use the strong passwords for the super user and the replication user as highlighted in the sample configuration file available.

Now, save the changes to the file and exit the nano editor.

Next, you need to configure the data directory.

In the Patroni configuration file, data directory is specified as *<mark>/data/patroni</mark>*. The superuser(*postgres*) mentioned in the configuration file, should be able to write into the data directory.

Create a directory patroni inside the <mark>/data/</mark> folder using the mkdir command as below.

```
<pre class="wp-block-code">```
sudo mkdir -p /data/patroni
```
```

Now, make the superuser *postgres* the owner of /data/patroni.

```
<pre class="wp-block-code">```
sudo chown postgres:postgres /data/patroni
```
```

In order to prevent anybody else from changing this directory, change the permissions on this directory to make it accessible only to the *postgres* user(owner of the directory).

```
<pre class="wp-block-code">```
sudo chmod 700 /data/patroni
```
```

Next, you need to create a systemd script that will allow us to start, stop and monitor Patroni. You can learn more about the systemd unit and unit file in [this](https://www.digitalocean.com/community/tutorials/understanding-systemd-units-and-unit-files) tutorial.

You need to create a file *<mark>/etc/systemd/system/patroni.service</mark>* using the nano command.

```
<pre class="wp-block-code">```
sudo nano /etc/systemd/system/patroni.service
```
```

Update the file with the below contents.

/etc/systemd/system/patroni.service

```
<pre class="wp-block-code config">```
[Unit]
Description=High availability PostgreSQL Cluster
After=syslog.target network.target

[Service]
Type=simple
User=postgres
Group=postgres
ExecStart=/usr/local/bin/patroni /etc/patroni/config.yml
KillMode=process
TimeoutSec=30
Restart=no

[Install]
WantedBy=multi-user.target
```
```

Save the changes to the file and exit the nano editor.

Now, you need to start Patroni for handling the postgres database.

The <mark>systemctl</mark> command is used to manage the *systemd* services.

Use <mark>start</mark> with <mark>systemctl</mark> to start the system service.

Execute the following command to start Patroni.

```
<pre class="wp-block-code">```
sudo systemctl start patroni
```
```

Now Patroni is running and its handling the postgresql database.

Use <mark>enable</mark> with <mark>systemctl</mark> to enable automatic start of Patroni service after every system reboot.

Execute the following command to enable automatic start of Patroni service after system reboot.

```
<pre class="wp-block-code">```
sudo systemctl enable patroni
```
```

You can use <mark>status</mark> with the <mark>systemctl</mark> to check the status of the system service.

Execute the following command to check the status of the Patroni service.

```
<pre class="wp-block-code">```
sudo systemctl status patroni
```
```

You will see the below messages if the Patroni configuration is successful.

```
<pre class="wp-block-code config">```
● patroni.service - High availability PostgreSQL Cluster
     Loaded: loaded (/etc/systemd/system/patroni.service; disabled; vendor preset: enabled)
     Active: active (running) since Fri 2020-08-28 00:41:53 UTC; 1 day 3h ago
   Main PID: 3045 (patroni)
      Tasks: 14 (limit: 1137)
     Memory: 76.4M
     CGroup: /system.slice/patroni.service
             ├─3045 /usr/bin/python3 /usr/local/bin/patroni /etc/patroni/config.yml
             ├─3071 postgres -D /data/patroni --config-file=/data/patroni/postgresql.conf --listen_addresses=128.199.30.42 --port=5432 --cluster_name=postgres --wal_level=replica --hot_standby=on --max_connections=100 --max_wal_senders=>
             ├─3076 postgres: postgres: checkpointer
             ├─3077 postgres: postgres: background writer
             ├─3078 postgres: postgres: stats collector
             ├─3083 postgres: postgres: postgres postgres 128.199.30.42(51028) idle
             ├─3183 postgres: postgres: walwriter
             ├─3184 postgres: postgres: autovacuum launcher
             ├─3185 postgres: postgres: logical replication launcher
             └─3191 postgres: postgres: walsender replicator 128.199.30.45(58144) streaming 0/5000550

Aug 29 04:19:41 do-01 patroni[3045]: 2020-08-29 04:19:41,453 INFO: Lock owner: node1; I am node1
Aug 29 04:19:41 do-01 patroni[3045]: 2020-08-29 04:19:41,458 INFO: no action.  i am the leader with the lock
Aug 29 04:19:51 do-01 patroni[3045]: 2020-08-29 04:19:51,453 INFO: Lock owner: node1; I am node1
Aug 29 04:19:51 do-01 patroni[3045]: 2020-08-29 04:19:51,458 INFO: no action.  i am the leader with the lock
Aug 29 04:20:01 do-01 patroni[3045]: 2020-08-29 04:20:01,453 INFO: Lock owner: node1; I am node1
Aug 29 04:20:01 do-01 patroni[3045]: 2020-08-29 04:20:01,459 INFO: no action.  i am the leader with the lock
Aug 29 04:20:11 do-01 patroni[3045]: 2020-08-29 04:20:11,453 INFO: Lock owner: node1; I am node1
Aug 29 04:20:11 do-01 patroni[3045]: 2020-08-29 04:20:11,458 INFO: no action.  i am the leader with the lock
Aug 29 04:20:21 do-01 patroni[3045]: 2020-08-29 04:20:21,453 INFO: Lock owner: node1; I am node1
Aug 29 04:20:21 do-01 patroni[3045]: 2020-08-29 04:20:21,460 INFO: no action.  i am the leader with the lock
```
```

Configuring Patroni in the first node is complete.

You need to follow the same steps in other two node(*node-2 and node-3*) where PostgreSQL is installed.

The specific sections to be updated are

- Node name
- IP Address of the respective node in the restapi section and the PostgreSQL section.

Once you complete the Patroni configuration in the node-2 and node-3, these nodes will join in the cluster and follow the leader node-1.

You can use status with the systemctl to check the status of the Patroni in node-2.

Execute the following command to check the status of the Patroni service.

```
<pre class="wp-block-code">```
sudo systemctl status patroni
```
```

You will see the below messages if the node-2 is joined in the cluster successfully.

```
<pre class="wp-block-code config">```
● patroni.service - High availability PostgreSQL Cluster
     Loaded: loaded (/etc/systemd/system/patroni.service; disabled; vendor preset: enabled)
     Active: active (running) since Thu 2020-08-27 14:05:32 UTC; 1 day 14h ago
   Main PID: 983 (patroni)
      Tasks: 12 (limit: 1137)
     Memory: 101.8M
     CGroup: /system.slice/patroni.service
             ├─ 983 /usr/bin/python3 /usr/local/bin/patroni /etc/patroni/config.yml
             ├─3617 postgres -D /data/patroni --config-file=/data/patroni/postgresql.conf --listen_addresses=128.199.30.45 --port=5432 --cluster_name=postgres --wal_level=replica --hot_standby=on --max_connections=100 --max_wal_senders=>
             ├─3619 postgres: postgres: startup   recovering 000000030000000000000005
             ├─3620 postgres: postgres: checkpointer
             ├─3621 postgres: postgres: background writer
             ├─3622 postgres: postgres: stats collector
             ├─3623 postgres: postgres: walreceiver   streaming 0/5000550
             └─3627 postgres: postgres: postgres postgres 128.199.30.45(57556) idle

Aug 29 04:23:11 do-02 patroni[983]: 2020-08-29 04:23:11,437 INFO: no action.  i am a secondary and i am following a leader
Aug 29 04:23:21 do-02 patroni[983]: 2020-08-29 04:23:21,432 INFO: Lock owner: node1; I am node2
Aug 29 04:23:21 do-02 patroni[983]: 2020-08-29 04:23:21,433 INFO: does not have lock
Aug 29 04:23:21 do-02 patroni[983]: 2020-08-29 04:23:21,437 INFO: no action.  i am a secondary and i am following a leader
Aug 29 04:23:31 do-02 patroni[983]: 2020-08-29 04:23:31,433 INFO: Lock owner: node1; I am node2
Aug 29 04:23:31 do-02 patroni[983]: 2020-08-29 04:23:31,433 INFO: does not have lock
Aug 29 04:23:31 do-02 patroni[983]: 2020-08-29 04:23:31,439 INFO: no action.  i am a secondary and i am following a leader
Aug 29 04:23:41 do-02 patroni[983]: 2020-08-29 04:23:41,434 INFO: Lock owner: node1; I am node2
Aug 29 04:23:41 do-02 patroni[983]: 2020-08-29 04:23:41,434 INFO: does not have lock
Aug 29 04:23:41 do-02 patroni[983]: 2020-08-29 04:23:41,439 INFO: no action.  i am a secondary and i am following a leader
```
```

Postgresql cluster is up and running.

Now, you’ll configure HAProxy which can be used to connect to Master Postgresql node.

## <span class="ez-toc-section" id="step_8_%e2%80%94_configuring_haproxy"></span>**Step 8 — Configuring HAProxy**<span class="ez-toc-section-end"></span>

HAProxy is free, open source software that provides a high availability load balancer and proxy server for TCP and HTTP-based applications that spreads requests across multiple servers…

You can use HAProxy to connect to the master node in the configured Postgresql cluster. All Postgres clients (your applications, psql, etc.) will connect to HAProxy which will make sure you connect to the master in the configured postgres cluster. You’ve installed it in node-5 in the step4 of the turorial.

During the installation of the HAProxy, a default haproxy.cfg file is created in the location *<mark>/etc/haproxy/haproxy.cfg</mark>*.

Execute the below command to open and update the configuration file.

```
<pre class="wp-block-code">```
sudo nano /etc/haproxy/haproxy.cfg
```
```

Update the file with the following content.

/etc/haproxy/haproxy.cfg

```
<pre class="wp-block-code  config"> ```
 global
    maxconn 100

defaults
    log global
    mode tcp
    retries 2
    timeout client 30m
    timeout connect 4s
    timeout server 30m
    timeout check 5s

listen stats
    mode http
    bind *:7000
    stats enable
    stats uri /

listen postgres
    bind *:5000
    option httpchk
    http-check expect status 200
    default-server inter 3s fall 3 rise 2 on-marked-down shutdown-sessions
    server postgresql_<span style="background-color: rgba(242,201,76,.35)">node-1-server-ip</span>_5432 <span style="background-color: rgba(242,201,76,.35)">node-1-server-ip</span>:5432 maxconn 100 check port 8008
    server postgresql_<span style="background-color: rgba(242,201,76,.35)">node-2-server-ip</span>_5432 <span style="background-color: rgba(242,201,76,.35)">node-2-server-ip</span>:5432 maxconn 100 check port 8008
    server postgresql_<span style="background-color: rgba(242,201,76,.35)">node-3-server-ip</span>_5432 <span style="background-color: rgba(242,201,76,.35)">node-3-server-ip</span>:5432 maxconn 100 check port 8008 
``` 
```

In the listen postgres section, you’ll update the details of the Postgres servers IPs which is used by HAProxy to connect to Postgres master server. You can learn more about HAProxy configuration parameters in the [official HAProxy docs page](http://cbonte.github.io/haproxy-dconv/2.2/configuration.html#2.5).

Save the changes to the file and exit the nano editor.

Now, you need to restart HAProxy for handling the high availability with the updated settings.

The <mark>systemctl</mark> command is used to manage the *systemd* services. Use <mark>restart</mark> with <mark>systemctl</mark> to start the system service.

Execute the following command to restart the HAProxy.

```
<pre class="wp-block-code">```
sudo systemctl restart haproxy
```
```

Use <mark>enable</mark> with <mark>systemctl</mark> to enable automatic start of HAProxy service after every system reboot.

Execute the following command to enable automatic start of HAProxy service after system reboot.

```
<pre class="wp-block-code">```
sudo systemctl enable haproxy
```
```

Now *HAProxy* is running and its handling the postgresql database instance with High availability.

Now, you can test the highly available postgresql cluster.

## <span class="ez-toc-section" id="step_9_%e2%80%94_testing_the_setup"></span>**Step 9 — Testing the Setup**<span class="ez-toc-section-end"></span>

You can test the highly available cluster using the HAProxy dashboard.

In your preferred web browser, enter the http://<mark>node-5-IP-address</mark>:7000 to open the HAProxy dashboard which looks like the below image.

<figure class="wp-block-image">![HAproxy dashboard page](http://149.28.53.131/wp-content/uploads/2020/11/HAproxy20dashboard20page-1.png)</figure>In the postgres section, the green highlighted line denotes the postgres node which is currently acting as the master. Now, shutdown the node-1 or stop the Patroni service in the node-1, you’ll be able to see another node from the cluster becomes the master. Refresh the HAProxy dashboard page and you’ll see the node-2 which has become the master as shown below.

<figure class="wp-block-image">![HAproxy dashboard page2](http://149.28.53.131/wp-content/uploads/2020/11/HAproxy20dashboard20page2-1.png)</figure>When you restart the node-1 or start the Patroni service, then node-1 will join the cluster, sync and follow the leader node-2.

You now have the highly available postgres up and running.

Your applications and postgres client can use the <mark>public-IP-address</mark> of the node-5 where HAProxy is installed with port 5000 to connect to this highly available cluster.

## <span class="ez-toc-section" id="conclusion"></span>**Conclusion**<span class="ez-toc-section-end"></span>

In this article, you have set up a robust and highly available PostgreSQL cluster.

Now you can improve it further by

- adding larger etcd cluster to improve availability
- adding HAProxy server and configure IP failover to create a highly available HAProxy cluster

## <span class="ez-toc-section" id="what_next"></span>What Next?<span class="ez-toc-section-end"></span>

[How to execute shell commands from Python?](https://www.stackvidhya.com/execute-system-command-or-shell-command-python/)

<div class="rank-math-block" id="rank-math-faq"><div class="rank-math-list "><div class="rank-math-list-item" id="faq-question-1605528251799">### <mark>how</mark> to install postgresql ubuntu?

<div class="rank-math-answer ">You can install Postgresql in ubuntu by using the command: sudo apt install postgresql postgresql-contrib

</div></div><div class="rank-math-list-item" id="faq-question-1605528320301">### What is high availability in PostgreSQL?

<div class="rank-math-answer ">High availabilty in Postgresql is a setup where the postgresql is setup in more than one machines and each machine acts as a node in the cluster. If the leader fails, other slave nodes available are automatically selected as leader. Hence, you can build systems without any database interruption.

</div></div><div class="rank-math-list-item" id="faq-question-1605528797666">### Does PostgreSQL support clustering?

<div class="rank-math-answer ">No, PostgreSQL doesn’t support clustering natively. However, it can be clustered using etcd and Patroni.

</div></div><div class="rank-math-list-item" id="faq-question-1605529039208">### Error patroni failed to get list of machines from

<div class="rank-math-answer ">This error occurs when the patroni is not able to communicate with your ETCD machine. Ensure the ports are correctly configured(Explained in the step1 of this tutorial.)

</div></div><div class="rank-math-list-item" id="faq-question-1605529179588">### system ID mismatch, node belongs to a different cluster – after reboot

<div class="rank-math-answer ">Ensure name, namespace and scope is correctly configured in the patroni configuration file(Explained in step-7 of this tutorial).

</div></div></div></div>