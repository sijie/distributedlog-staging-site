<!DOCTYPE html>
<html lang="en">

  <head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>Apache DistributedLog</title>
  <meta name="description" content="Apache DistributedLog is an high performance replicated log.
">

  <link rel="stylesheet" href="/distributedlog-staging-site/styles/site.css">
  <link rel="stylesheet" href="/distributedlog-staging-site/css/theme.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js"></script>
  <script src="/distributedlog-staging-site/js/bootstrap.min.js"></script>
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/latest/admin_guide/bookkeeper.rst" data-proofer-ignore>
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
        .. contents:: BookKeeper

BookKeeper
==========

For reliable BookKeeper service, you should deploy BookKeeper in a cluster.

Run from bookkeeper source
--------------------------

The version of BookKeeper that DistributedLog depends on is not the official opensource version.
It is twitter's production version `4.3.4-TWTTR`, which is available in `https://github.com/twitter/bookkeeper`. 
We are working actively with BookKeeper community to merge all twitter's changes back to the community.

The major changes in Twitter's bookkeeper includes:

- BOOKKEEPER-670_: Long poll reads and LastAddConfirmed piggyback. It is to reduce the tailing read latency.
- BOOKKEEPER-759_: Delay ensemble change if it doesn't break ack quorum constraint. It is to reduce the write latency on bookie failures.
- BOOKKEEPER-757_: Ledger recovery improvements, to reduce the latency on ledger recovery.
- Misc improvements on bookie recovery and bookie storage.

.. _BOOKKEEPER-670: https://issues.apache.org/jira/browse/BOOKKEEPER-670
.. _BOOKKEEPER-759: https://issues.apache.org/jira/browse/BOOKKEEPER-759
.. _BOOKKEEPER-757: https://issues.apache.org/jira/browse/BOOKKEEPER-757

To build bookkeeper, run:

1. First checkout the bookkeeper source code from twitter's branch.

.. code-block:: bash

    $ git clone https://github.com/twitter/bookkeeper.git bookkeeper   


2. Build the bookkeeper package:

.. code-block:: bash

    $ cd bookkeeper 
    $ mvn clean package assembly:single -DskipTests

However, since `bookkeeper-server` is one of the dependency of `distributedlog-proxy-server`.
You could simply run bookkeeper using same set of scripts provided in `distributedlog-proxy-server`.
In the following sections, we will describe how to run bookkeeper using the scripts provided in
`distributedlog-proxy-server`.

Run from distributedlog source
------------------------------

Build
+++++

First of all, build DistributedLog:

.. code-block:: bash

    $ mvn clean install -DskipTests


Configuration
+++++++++++++

The configuration file `bookie.conf` under `distributedlog-proxy-server/conf` is a template of production
configuration to run a bookie node. Most of the configuration settings are good for production usage.
You might need to configure following settings according to your environment and hardware platform.

Port
^^^^

By default, the service port is `3181`, where the bookie server listens on. You can change the port
to whatever port you like by modifying the following setting.

::

    bookiePort=3181


Disks
^^^^^

You need to configure following settings according to the disk layout of your hardware. It is recommended
to put `journalDirectory` under a separated disk from others for performance. It is okay to set
`indexDirectories` to be same as `ledgerDirectories`. However, it is recommended to put `indexDirectories`
to a SSD driver for better performance.

::
    
    # Directory Bookkeeper outputs its write ahead log
    journalDirectory=/tmp/data/bk/journal

    # Directory Bookkeeper outputs ledger snapshots
    ledgerDirectories=/tmp/data/bk/ledgers

    # Directory in which index files will be stored.
    indexDirectories=/tmp/data/bk/ledgers


To better understand how bookie nodes work, please check bookkeeper_ website for more details.

ZooKeeper
^^^^^^^^^

You need to configure following settings to point the bookie to the zookeeper server that it is using.
You need to make sure `zkLedgersRootPath` exists before starting the bookies.

::
   
    # Root zookeeper path to store ledger metadata
    # This parameter is used by zookeeper-based ledger manager as a root znode to
    # store all ledgers.
    zkLedgersRootPath=/messaging/bookkeeper/ledgers
    # A list of one of more servers on which zookeeper is running.
    zkServers=localhost:2181


Stats Provider
^^^^^^^^^^^^^^

Bookies use `StatsProvider` to expose its metrics. The `StatsProvider` is a pluggable library to
adopt to various stats collecting systems. Please check monitoring_ for more details.

.. _monitoring: ./monitoring

::
    
    # stats provide - use `codahale` metrics library
    statsProviderClass=org.apache.bookkeeper.stats.CodahaleMetricsServletProvider

    ### Following settings are stats provider related settings

    # Exporting codahale stats in http port `9001`
    codahaleStatsHttpPort=9001


Index Settings
^^^^^^^^^^^^^^

- `pageSize`: size of a index page in ledger cache, in bytes. If there are large number
  of ledgers and each ledger has fewer entries, smaller index page would improve memory usage.
- `pageLimit`: The maximum number of index pages in ledger cache. If nummber of index pages
  reaches the limitation, bookie server starts to swap some ledgers from memory to disk.
  Increase this value when swap becomes more frequent. But make sure `pageLimit*pageSize`
  should not be more than JVM max memory limitation.


Journal Settings
^^^^^^^^^^^^^^^^

- `journalMaxGroupWaitMSec`: The maximum wait time for group commit. It is valid only when
  `journalFlushWhenQueueEmpty` is false.
- `journalFlushWhenQueueEmpty`: Flag indicates whether to flush/sync journal. If it is `true`,
  bookie server will sync journal when there is no other writes in the journal queue.
- `journalBufferedWritesThreshold`: The maximum buffered writes for group commit, in bytes.
  It is valid only when `journalFlushWhenQueueEmpty` is false.
- `journalBufferedEntriesThreshold`: The maximum buffered writes for group commit, in entries.
  It is valid only when `journalFlushWhenQueueEmpty` is false.

Setting `journalFlushWhenQueueEmpty` to `true` will produce low latency when the traffic is low.
However, the latency varies a lost when the traffic is increased. So it is recommended to set
`journalMaxGroupWaitMSec`, `journalBufferedEntriesThreshold` and `journalBufferedWritesThreshold`
to reduce the number of fsyncs made to journal disk, to achieve sustained low latency.

Thread Settings
^^^^^^^^^^^^^^^

It is recommended to configure following settings to align with the cpu cores of the hardware.

::
    
    numAddWorkerThreads=4
    numJournalCallbackThreads=4
    numReadWorkerThreads=4
    numLongPollWorkerThreads=4

Run 
+++

As `bookkeeper-server` is shipped as part of `distributedlog-proxy-server`, you could use the `dlog-daemon.sh`
script to start `bookie` as daemon thread.

Start the bookie:

.. code-block:: bash

    $ ./distributedlog-proxy-server/bin/dlog-daemon.sh start bookie --conf /path/to/bookie/conf


Stop the bookie:

.. code-block:: bash

    $ ./distributedlog-proxy-server/bin/dlog-daemon.sh stop bookie


Please check bookkeeper_ website for more details.

.. _bookkeeper: http://bookkeeper.apache.org/

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
