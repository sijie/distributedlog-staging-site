<!DOCTYPE html>
<html lang="en">

  <head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>Cluster Setup</title>
  <meta name="description" content="Apache DistributedLog is an high performance replicated log.
">

  <link rel="stylesheet" href="/distributedlog-staging-site/styles/site.css">
  <link rel="stylesheet" href="/distributedlog-staging-site/css/theme.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js"></script>
  <script src="/distributedlog-staging-site/js/bootstrap.min.js"></script>
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/latest/deployment/cluster.rst" data-proofer-ignore>
  <link rel="alternate" type="application/rss+xml" title="Apache DistributedLog" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/feed.xml">
  <script>
  (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
  (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new Date();a=s.createElement(o),
  m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
  })(window,document,'script','https://www.google-analytics.com/analytics.js','ga');

  ga('create', 'UA-83870961-1', 'auto');
  ga('send', 'pageview');

  </script> 
  <link rel="shortcut icon" type="image/x-icon" href="/images/favicon.ico">
</head>


  <body role="document">

    <nav class="navbar navbar-default navbar-fixed-top">
  <div class="container">
    <div class="navbar-header">
      <a href="/" class="navbar-brand" >
        <img alt="Brand" style="height: 28px" src="/distributedlog-staging-site/images/distributedlog_logo_navbar.png">
      </a>
      <button type="button" class="navbar-toggle collapsed" data-toggle="collapse" data-target="#navbar" aria-expanded="false" aria-controls="navbar">
        <span class="sr-only">Toggle navigation</span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
      </button>
    </div>
    <div id="navbar" class="navbar-collapse collapse">
      <ul class="nav navbar-nav">
        <!-- Overview -->
        <li><a href="/distributedlog-staging-site/docs/latest/basics/introduction">Overview</a></li>
        <!-- Downloads -->
        <li><a href="/distributedlog-staging-site/docs/latest/start/download">Downloads</a></li>
        <!-- Quick Start -->
        <li class="dropdown">
          <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Quick Start<span class="caret"></span></a>
          <ul class="dropdown-menu">
            <li><a href="/distributedlog-staging-site/docs/latest/start/quickstart">Setup & Run Example</a></li>
            <li role="separator" class="divider"></li>
            <li class="dropdown-header">Tutorials</li>
            <li>
              <a href="/distributedlog-staging-site/docs/latest/tutorials/main#id3">
              <small><span class="glyphicon glyphicon-pencil"></span></small>
              Basic
              </a>
            </li>
            <li>
              <a href="/distributedlog-staging-site/docs/latest/tutorials/main#id4">
              <small><span class="glyphicon glyphicon-envelope"></span></small>
              Messaging
              </a>
            </li>
            <li>
              <a href="/distributedlog-staging-site/docs/latest/tutorials/main#id6">
              <small><span class="glyphicon glyphicon-stats"></span></small>
              Analytics
              </a>
            </li>
          </ul>
        </li>
        <!-- Documentation -->
        <li class="dropdown">
		      <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Documentation<span class="caret"></span></a>
          <ul class="dropdown-menu">
            <li class="dropdown-header">Snapshot (Developement)</li>
            <li><a href="/distributedlog-staging-site/docs/latest">0.5.0-SNAPSHOT</a></li>
            <li role="separator" class="divider"></li>
            <li class="dropdown-header">Releases</li>
            <li><a href="/distributedlog-staging-site/docs/0.4.0-incubating">0.4.0-incubating</a></li>
            <li role="separator" class="divider"></li>
            <li>
              <a href="https://cwiki.apache.org/confluence/display/DL/Project+Ideas">
                <small><span class="glyphicon glyphicon-new-window"></span></small>
                Project Ideas
              </a>
            </li>
          </ul>
        </li>
        <!-- FAQ -->
        <li><a href="/distributedlog-staging-site/faq">FAQ</a></li>
      </ul>
      <!-- Right Side -->
      <ul class="nav navbar-nav navbar-right">
        <!-- Blog -->
        <li><a href="/distributedlog-staging-site/blog">Blog</a></li>
        <!-- Community -->
        <li class="dropdown">
          <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Community<span class="caret"></span></a>
          <ul class="dropdown-menu">
            <li class="dropdown-header">Community</li>
            <li><a href="/distributedlog-staging-site/community/#mailing-lists">Mailing Lists</a></li>
            <li><a href="/distributedlog-staging-site/community/#source-code">Source Code</a></li>
            <li><a href="/distributedlog-staging-site/community/#issue-tracker">Issue Tracking</a></li>
            <li><a href="/distributedlog-staging-site/community/team/">Team</a></li>
            <li role="separator" class="divider"></li>
            <li class="dropdown-header">Contribute</li>
            <li><a href="https://cwiki.apache.org/confluence/display/DL/Developer+Setup">Developer Setup</a></li>
            <li><a href="https://cwiki.apache.org/confluence/display/DL/Contributing+to+DistributedLog">Contributing to DistributedLog</a></li>
            <li><a href="https://cwiki.apache.org/confluence/pages/viewpage.action?pageId=65867477">Coding Guide</a></li>
            <li role="separator" class="divider"></li>
            <li class="dropdown-header">Guides</li>
            <li><a href="/distributedlog-staging-site/community/release-guide">Release Guide</a></li>
          </ul>
        </li>
        <!-- Project -->
        <li class="dropdown">
          <a href="#" class="dropdown-toggle" data-toggle="dropdown" role="button" aria-haspopup="true" aria-expanded="false">Project<span class="caret"></span></a>
          <ul class="dropdown-menu">
			      <li class="dropdown-header">Project</li>
            <li><a href="/distributedlog-staging-site/project/presentations/">Presentations</a></li>
            <li>
              <a href="https://twitter.com/distributedlog">
                <small><span class="glyphicon glyphicon-new-window"></span></small>
                Twitter
              </a>
            </li>
            <li>
              <a href="https://github.com/apache/distributedlog">
                <small><span class="glyphicon glyphicon-new-window"></span></small>
                Github
              </a>
            </li>
            <li>
              <a href="https://getdl-slack.herokuapp.com">
                <small><span class="glyphicon glyphicon-new-window"></span></small>
                Slack
              </a>
            </li>
            <li>
              <a href="https://cwiki.apache.org/confluence/display/DL/Apache+DistributedLog+Home">
                <small><span class="glyphicon glyphicon-new-window"></span></small>
                Wiki
              </a>
            </li>
          </ul>
        </li>
      </ul>
    </div><!--/.nav-collapse -->
  </div>
</nav>


<link rel="stylesheet" href="">


    <div class="container" role="main">

      <div class="row">
        .. contents:: This page provides instructions on how to run **DistributedLog** in a fully distributed fashion.

Cluster Setup & Deployment
==========================

This section describes how to run DistributedLog in `distributed` mode.
To run a cluster with DistributedLog, you need a Zookeeper cluster and a Bookkeeper cluster.

Build
-----

To build DistributedLog, run:

.. code-block:: bash

   mvn clean install -DskipTests


Or run `./scripts/snapshot` to build the release packages from current source. The released
packages contain the binaries for running `distributedlog-proxy-server`, `distributedlog-benchmark`
and `distributedlog-tutorials`.

NOTE: we run the following instructions from distributedlog source code after
running `mvn clean install`.  And assume `DL_HOME` is the directory of
distributedlog source.

Zookeeper
---------

(If you already have a zookeeper cluster running, you could skip this section.)

We could use the `dlog-daemon.sh` and the `zookeeper.conf.template` to demonstrate run a 1-node
zookeeper ensemble locally.

Create a `zookeeper.conf` from the `zookeeper.conf.template`.

.. code-block:: bash

    $ cp distributedlog-proxy-server/conf/zookeeper.conf.template distributedlog-proxy-server/conf/zookeeper.conf

Configure the settings in `zookeeper.conf`. By default, it will use `/tmp/data/zookeeper` for storing
the zookeeper data. Let's create the data directories for zookeeper.

.. code-block:: bash

    $ mkdir -p /tmp/data/zookeeper/txlog

Once the data directory is created, we need to assign `myid` for this zookeeper node.

.. code-block:: bash

    $ echo "1" > /tmp/data/zookeeper/myid

Start the zookeeper daemon using `dlog-daemon.sh`.

.. code-block:: bash

    $ ./distributedlog-proxy-server/bin/dlog-daemon.sh start zookeeper ${DL_HOME}/distributedlog-proxy-server/conf/zookeeper.conf

You could verify the zookeeper setup using `zkshell`.

.. code-block:: bash

    // ./distributedlog-proxy-server/bin/dlog zkshell ${zkservers}
    $ ./distributedlog-proxy-server/bin/dlog zkshell localhost:2181
    Connecting to localhost:2181
    Welcome to ZooKeeper!
    JLine support is enabled

    WATCHER::

    WatchedEvent state:SyncConnected type:None path:null
    [zk: localhost:2181(CONNECTED) 0] ls /
    [zookeeper]
    [zk: localhost:2181(CONNECTED) 1]

Please refer to the `ZooKeeper Guide`_ for more details on setting up zookeeper cluster.

.. _ZooKeeper Guide: ../admin_guide/zookeeper

Bookkeeper
----------

(If you already have a bookkeeper cluster running, you could skip this section.)

We could use the `dlog-daemon.sh` and the `bookie.conf.template` to demonstrate run a 3-nodes
bookkeeper cluster locally.

Create a `bookie.conf` from the `bookie.conf.template`. Since we are going to run a 3-nodes
bookkeeper cluster locally. Let's make three copies of `bookie.conf.template`.

.. code-block:: bash

    $ cp distributedlog-proxy-server/conf/bookie.conf.template distributedlog-proxy-server/conf/bookie-1.conf
    $ cp distributedlog-proxy-server/conf/bookie.conf.template distributedlog-proxy-server/conf/bookie-2.conf
    $ cp distributedlog-proxy-server/conf/bookie.conf.template distributedlog-proxy-server/conf/bookie-3.conf

Configure the settings in the bookie configuraiont files.

First of all, choose the zookeeper cluster that the bookies will use and set `zkServers` in
the configuration files.

::

    zkServers=localhost:2181


Choose the zookeeper path to store bookkeeper metadata and set `zkLedgersRootPath` in the configuration
files. Let's use `/messaging/bookkeeper/ledgers` in this instruction.

::

    zkLedgersRootPath=/messaging/bookkeeper/ledgers


Format bookkeeper metadata
++++++++++++++++++++++++++

(NOTE: only format bookkeeper metadata when first time setting up the bookkeeper cluster.)

The bookkeeper shell doesn't automatically create the `zkLedgersRootPath` when running `metaformat`.
So using `zkshell` to create the `zkLedgersRootPath`.

::

    $ ./distributedlog-proxy-server/bin/dlog zkshell localhost:2181
    Connecting to localhost:2181
    Welcome to ZooKeeper!
    JLine support is enabled

    WATCHER::

    WatchedEvent state:SyncConnected type:None path:null
    [zk: localhost:2181(CONNECTED) 0] create /messaging ''
    Created /messaging
    [zk: localhost:2181(CONNECTED) 1] create /messaging/bookkeeper ''
    Created /messaging/bookkeeper
    [zk: localhost:2181(CONNECTED) 2] create /messaging/bookkeeper/ledgers ''
    Created /messaging/bookkeeper/ledgers
    [zk: localhost:2181(CONNECTED) 3]


If the `zkLedgersRootPath`, run `metaformat` to format the bookkeeper metadata.

::

    $ BOOKIE_CONF=${DL_HOME}/distributedlog-proxy-server/conf/bookie-1.conf ./distributedlog-proxy-server/bin/dlog bkshell metaformat
    Are you sure to format bookkeeper metadata ? (Y or N) Y

Add Bookies
+++++++++++

Once the bookkeeper metadata is formatted, it is ready to add bookie nodes to the cluster.

Configure Ports
^^^^^^^^^^^^^^^

Configure the ports that used by bookies.

bookie-1:

::

    # Port that bookie server listen on
    bookiePort=3181
    # Exporting codahale stats
    185 codahaleStatsHttpPort=9001

bookie-2:

::

    # Port that bookie server listen on
    bookiePort=3182
    # Exporting codahale stats
    185 codahaleStatsHttpPort=9002

bookie-3:

::

    # Port that bookie server listen on
    bookiePort=3183
    # Exporting codahale stats
    185 codahaleStatsHttpPort=9003

Configure Disk Layout
^^^^^^^^^^^^^^^^^^^^^

Configure the disk directories used by a bookie server by setting following options.

::

    # Directory Bookkeeper outputs its write ahead log
    journalDirectory=/tmp/data/bk/journal
    # Directory Bookkeeper outputs ledger snapshots
    ledgerDirectories=/tmp/data/bk/ledgers
    # Directory in which index files will be stored.
    indexDirectories=/tmp/data/bk/ledgers

As we are configuring a 3-nodes bookkeeper cluster, we modify the following settings as below:

bookie-1:

::

    # Directory Bookkeeper outputs its write ahead log
    journalDirectory=/tmp/data/bk-1/journal
    # Directory Bookkeeper outputs ledger snapshots
    ledgerDirectories=/tmp/data/bk-1/ledgers
    # Directory in which index files will be stored.
    indexDirectories=/tmp/data/bk-1/ledgers

bookie-2:

::

    # Directory Bookkeeper outputs its write ahead log
    journalDirectory=/tmp/data/bk-2/journal
    # Directory Bookkeeper outputs ledger snapshots
    ledgerDirectories=/tmp/data/bk-2/ledgers
    # Directory in which index files will be stored.
    indexDirectories=/tmp/data/bk-2/ledgers

bookie-3:

::

    # Directory Bookkeeper outputs its write ahead log
    journalDirectory=/tmp/data/bk-3/journal
    # Directory Bookkeeper outputs ledger snapshots
    ledgerDirectories=/tmp/data/bk-3/ledgers
    # Directory in which index files will be stored.
    indexDirectories=/tmp/data/bk-3/ledgers

Format bookie
^^^^^^^^^^^^^

Once the disk directories are configured correctly in the configuration file, use
`bkshell bookieformat` to format the bookie.

::

    BOOKIE_CONF=${DL_HOME}/distributedlog-proxy-server/conf/bookie-1.conf ./distributedlog-proxy-server/bin/dlog bkshell bookieformat
    BOOKIE_CONF=${DL_HOME}/distributedlog-proxy-server/conf/bookie-2.conf ./distributedlog-proxy-server/bin/dlog bkshell bookieformat
    BOOKIE_CONF=${DL_HOME}/distributedlog-proxy-server/conf/bookie-3.conf ./distributedlog-proxy-server/bin/dlog bkshell bookieformat


Start bookie
^^^^^^^^^^^^

Start the bookie using `dlog-daemon.sh`.

::

    SERVICE_PORT=3181 ./distributedlog-proxy-server/bin/dlog-daemon.sh start bookie --conf ${DL_HOME}/distributedlog-proxy-server/conf/bookie-1.conf
    SERVICE_PORT=3182 ./distributedlog-proxy-server/bin/dlog-daemon.sh start bookie --conf ${DL_HOME}/distributedlog-proxy-server/conf/bookie-2.conf
    SERVICE_PORT=3183 ./distributedlog-proxy-server/bin/dlog-daemon.sh start bookie --conf ${DL_HOME}/distributedlog-proxy-server/conf/bookie-3.conf

Verify whether the bookie is setup correctly. You could simply check whether the bookie is showed up in
zookeeper `zkLedgersRootPath`/available znode.

::

    $ ./distributedlog-proxy-server/bin/dlog zkshell localhost:2181
    Connecting to localhost:2181
    Welcome to ZooKeeper!
    JLine support is enabled

    WATCHER::

    WatchedEvent state:SyncConnected type:None path:null
    [zk: localhost:2181(CONNECTED) 0] ls /messaging/bookkeeper/ledgers/available
    [127.0.0.1:3181, 127.0.0.1:3182, 127.0.0.1:3183, readonly]
    [zk: localhost:2181(CONNECTED) 1]


Or check if the bookie is exposing the stats at port `codahaleStatsHttpPort`.

::

    // ping the service
    $ curl localhost:9001/ping
    pong
    // checking the stats
    curl localhost:9001/metrics?pretty=true

Stop bookie
^^^^^^^^^^^

Stop the bookie using `dlog-daemon.sh`.

::

    $ ./distributedlog-proxy-server/bin/dlog-daemon.sh stop bookie
    // Example:
    $ SERVICE_PORT=3181 ./distributedlog-proxy-server/bin/dlog-daemon.sh stop bookie
    doing stop bookie ...
    stopping bookie
    Shutdown is in progress... Please wait...
    Shutdown completed.

Turn bookie to readonly
^^^^^^^^^^^^^^^^^^^^^^^

Start the bookie in `readonly` mode.

::

    $ SERVICE_PORT=3181 ./distributedlog-proxy-server/bin/dlog-daemon.sh start bookie --conf ${DL_HOME}/distributedlog-proxy-server/conf/bookie-1.conf --readonly

Verify if the bookie is running in `readonly` mode.

::

    $ ./distributedlog-proxy-server/bin/dlog zkshell localhost:2181
    Connecting to localhost:2181
    Welcome to ZooKeeper!
    JLine support is enabled

    WATCHER::

    WatchedEvent state:SyncConnected type:None path:null
    [zk: localhost:2181(CONNECTED) 0] ls /messaging/bookkeeper/ledgers/available
    [127.0.0.1:3182, 127.0.0.1:3183, readonly]
    [zk: localhost:2181(CONNECTED) 1] ls /messaging/bookkeeper/ledgers/available/readonly
    [127.0.0.1:3181]
    [zk: localhost:2181(CONNECTED) 2]

Please refer to the `BookKeeper Guide`_ for more details on setting up bookkeeper cluster.

.. _BookKeeper Guide: ../admin_guide/bookkeeper

Create Namespace
----------------

After setting up a zookeeper cluster and a bookkeeper cluster, you could provision DL namespaces
for applications to use.

Provisioning a DistributedLog namespace is accomplished via the `bind` command available in `dlog tool`.

Namespace is bound by writing bookkeeper environment settings (e.g. the ledger path, bkLedgersZkPath,
or the set of Zookeeper servers used by bookkeeper, bkZkServers) as metadata in the zookeeper path of
the namespace DL URI. The DL library resolves the DL URI to determine which bookkeeper cluster it
should read and write to. 

The namespace binding has following features:

- `Inheritance`: suppose `distributedlog://<zkservers>/messaging/distributedlog` is bound to bookkeeper
  cluster `X`. All the streams created under `distributedlog://<zkservers>/messaging/distributedlog`,
  will write to bookkeeper cluster `X`.
- `Override`: suppose `distributedlog://<zkservers>/messaging/distributedlog` is bound to bookkeeper
  cluster `X`. You want streams under `distributedlog://<zkservers>/messaging/distributedlog/S` write
  to bookkeeper cluster `Y`. You could just bind `distributedlog://<zkservers>/messaging/distributedlog/S`
  to bookkeeper cluster `Y`. The binding to `distributedlog://<zkservers>/messaging/distributedlog/S`
  only affects streams under `distributedlog://<zkservers>/messaging/distributedlog/S`.

Create namespace binding using `dlog tool`. For example, we create a namespace
`distributedlog://127.0.0.1:2181/messaging/distributedlog/mynamespace` pointing to the
bookkeeper cluster we just created above.

::

    $ distributedlog-proxy-server/bin/dlog admin bind \\
        -dlzr 127.0.0.1:2181 \\
        -dlzw 127.0.0.1:2181 \\
        -s 127.0.0.1:2181 \\
        -bkzr 127.0.0.1:2181 \\
        -l /messaging/bookkeeper/ledgers \\
        -i false \\
        -r true \\
        -c \\
        distributedlog://127.0.0.1:2181/messaging/distributedlog/mynamespace

    No bookkeeper is bound to distributedlog://127.0.0.1:2181/messaging/distributedlog/mynamespace
    Created binding on distributedlog://127.0.0.1:2181/messaging/distributedlog/mynamespace.


- Configure the zookeeper cluster used for storing DistributedLog metadata: `-dlzr` and `-dlzw`.
  Ideally `-dlzr` and `-dlzw` would be same the zookeeper server in distributedlog namespace uri.
  However to scale zookeeper reads, the zookeeper observers sometimes are added in a different
  domain name than participants. In such case, configuring `-dlzr` and `-dlzw` to different
  zookeeper domain names would help isolating zookeeper write and read traffic.
- Configure the zookeeper cluster used by bookkeeper for storing the metadata : `-bkzr` and `-s`.
  Similar as `-dlzr` and `-dlzw`, you could configure the namespace to use different zookeeper
  domain names for readers and writers to access bookkeeper metadatadata.
- Configure the bookkeeper ledgers path: `-l`.
- Configure the zookeeper path to store DistributedLog metadata. It is implicitly included as part
  of namespace URI.

Write Proxy
-----------

A write proxy consists of multiple write proxies. They don't store any state locally. So they are
mostly stateless and can be run as many as you can.

Configuration
+++++++++++++

Different from bookkeeper, DistributedLog tries not to configure any environment related settings
in configuration files. Any environment related settings are stored and configured via `namespace binding`.
The configuration file should contain non-environment related settings.

There is a `write_proxy.conf` template file available under `distributedlog-proxy-server` module.

Run write proxy
+++++++++++++++

A write proxy could be started using `dlog-daemon.sh` script under `distributedlog-proxy-server`.

::

    WP_SHARD_ID=${WP_SHARD_ID} WP_SERVICE_PORT=${WP_SERVICE_PORT} WP_STATS_PORT=${WP_STATS_PORT} ./distributedlog-proxy-server/bin/dlog-daemon.sh start writeproxy

- `WP_SHARD_ID`: A non-negative integer. You don't need to guarantee uniqueness of shard id, as it is just an
  indicator to the client for routing the requests. If you are running the `write proxy` using a cluster scheduler
  like `aurora`, you could easily obtain a shard id and use that to configure `WP_SHARD_ID`.
- `WP_SERVICE_PORT`: The port that write proxy listens on.
- `WP_STATS_PORT`: The port that write proxy exposes stats to a http endpoint.

Please check `distributedlog-proxy-server/conf/dlogenv.sh` for more environment variables on configuring write proxy.

- `WP_CONF_FILE`: The path to the write proxy configuration file.
- `WP_NAMESPACE`: The distributedlog namespace that the write proxy is serving for.

For example, we start 3 write proxies locally and point to the namespace created above.

::

    $ WP_SHARD_ID=1 WP_SERVICE_PORT=4181 WP_STATS_PORT=20001 ./distributedlog-proxy-server/bin/dlog-daemon.sh start writeproxy
    $ WP_SHARD_ID=2 WP_SERVICE_PORT=4182 WP_STATS_PORT=20002 ./distributedlog-proxy-server/bin/dlog-daemon.sh start writeproxy
    $ WP_SHARD_ID=3 WP_SERVICE_PORT=4183 WP_STATS_PORT=20003 ./distributedlog-proxy-server/bin/dlog-daemon.sh start writeproxy

The write proxy will announce itself to the zookeeper path `.write_proxy` under the dl namespace path.

We could verify that the write proxy is running correctly by checking the zookeeper path or checking its stats port.

::

    $ ./distributedlog-proxy-server/bin/dlog zkshell localhost:2181
    Connecting to localhost:2181
    Welcome to ZooKeeper!
    JLine support is enabled

    WATCHER::

    WatchedEvent state:SyncConnected type:None path:null
    [zk: localhost:2181(CONNECTED) 0] ls /messaging/distributedlog/mynamespace/.write_proxy
    [member_0000000000, member_0000000001, member_0000000002]


::

    $ curl localhost:20001/ping
    pong


Add and Remove Write Proxies
++++++++++++++++++++++++++++

Removing a write proxy is pretty straightforward by just killing the process.

::

    WP_SHARD_ID=1 WP_SERVICE_PORT=4181 WP_STATS_PORT=10001 ./distributedlog-proxy-server/bin/dlog-daemon.sh stop writeproxy


Adding a new write proxy is just adding a new host and starting the write proxy
process as described above.

Write Proxy Naming
++++++++++++++++++

The `dlog-daemon.sh` script starts the write proxy by announcing it to the `.write_proxy` path under
the dl namespace. So you could use uri in the distributedlog client builder to access the write proxy cluster.

Verify the setup
++++++++++++++++

You could verify the write proxy cluster by running tutorials over the setup cluster.

Create 10 streams.

::
    
    $ ./distributedlog-proxy-server/bin/dlog tool create -u distributedlog://127.0.0.1:2181/messaging/distributedlog/mynamespace -r stream- -e 0-10
    You are going to create streams : [stream-0, stream-1, stream-2, stream-3, stream-4, stream-5, stream-6, stream-7, stream-8, stream-9, stream-10] (Y or N) Y


Tail read from the 10 streams.

::

    $ ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.MultiReader distributedlog://127.0.0.1:2181/messaging/distributedlog/mynamespace stream-0,stream-1,stream-2,stream-3,stream-4,stream-5,stream-6,stream-7,stream-8,stream-9,stream-10


Run record generator over some streams

::

    $ ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.RecordGenerator 'zk!127.0.0.1:2181!/messaging/distributedlog/mynamespace/.write_proxy' stream-0 100
    $ ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.RecordGenerator 'zk!127.0.0.1:2181!/messaging/distributedlog/mynamespace/.write_proxy' stream-1 100


Check the terminal running `MultiReader`. You will see similar output as below:

::

    """
    Received record DLSN{logSegmentSequenceNo=1, entryId=21044, slotId=0} from stream stream-0
    """
    record-1464085079105
    """
    Received record DLSN{logSegmentSequenceNo=1, entryId=21046, slotId=0} from stream stream-0
    """
    record-1464085079113
    """
    Received record DLSN{logSegmentSequenceNo=1, entryId=9636, slotId=0} from stream stream-1
    """
    record-1464085079110
    """
    Received record DLSN{logSegmentSequenceNo=1, entryId=21048, slotId=0} from stream stream-0
    """
    record-1464085079125
    """
    Received record DLSN{logSegmentSequenceNo=1, entryId=9638, slotId=0} from stream stream-1
    """
    record-1464085079121
    """
    Received record DLSN{logSegmentSequenceNo=1, entryId=21050, slotId=0} from stream stream-0
    """
    record-1464085079133
    """
    Received record DLSN{logSegmentSequenceNo=1, entryId=9640, slotId=0} from stream stream-1
    """
    record-1464085079130
    """



Please refer to the Performance_ page for more details on tuning performance.

.. _Performance: ../admin_guide/performance

      </div>


    <hr>
  <div class="row">
      <div class="col-xs-12">
          <footer>
              <p class="text-center">&copy; Copyright 2016
                  <a href="http://www.apache.org">The Apache Software Foundation.</a> All Rights Reserved.
              </p>
              <p class="text-center">
                  <a href="/distributedlog-staging-site/feed.xml">RSS Feed</a>
              </p>
          </footer>
      </div>
  </div>
  <!-- container div end -->
</div>


  </body>

</html>
