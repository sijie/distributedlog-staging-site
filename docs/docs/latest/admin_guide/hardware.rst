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
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/latest/admin_guide/hardware.rst" data-proofer-ignore>
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
        .. contents:: Hardware

Hardware
========

Figure 1 describes the data flow of DistributedLog. Write traffic comes to `Write Proxy`
and the data is replicated in `RF` (replication factor) ways to `BookKeeper`. BookKeeper
stores the replicated data and keeps the data for a given retention period. The data is
read by `Read Proxy` and fanout to readers.

In such layered architecture, each layer has its own responsibilities and different resource
requirements. It makes the capacity and cost model much clear and users could scale
different layers independently.

.. figure:: ../images/costmodel.png
   :align: center

   Figure 1. DistributedLog Cost Model

Metrics
~~~~~~~

There are different metrics measuring the capability of a service instance in each layer
(e.g a `write proxy` node, a `bookie` storage node, a `read proxy` node and such). These metrics
can be `rps` (requests per second), `bps` (bits per second), `number of streams` that a instance
can support, and latency requirements. `bps` is the best and simple factor on measuring the
capability of current distributedlog architecture.

Write Proxy
~~~~~~~~~~~

Write Proxy (WP) is a stateless serving service that writes and replicates fan-in traffic into BookKeeper.
The capability of a write proxy instance is purely dominated by the *OUTBOUND* network bandwidth,
which is reflected as incoming `Write Throughput` and `Replication Factor`.

Calculating the capacity of Write Proxy (number of instances of write proxies) is pretty straightforward.
The formula is listed as below.

::

    Number of Write Proxies = (Write Throughput) * (Replication Factor) / (Write Proxy Outbound Bandwidth)

As it is bandwidth bound, we'd recommend using machines that have high network bandwith (e.g 10Gb NIC).

The cost estimation is also straightforward.

::

    Bandwidth TCO ($/day/MB) = (Write Proxy TCO) / (Write Proxy Outbound Bandwidth)
    Cost of write proxies = (Write Throughput) * (Replication Factor) / (Bandwidth TCO)

CPUs
^^^^

DistributedLog is not CPU bound. You can run an instance with 8 or 12 cores just fine.

Memories
^^^^^^^^

There's a fair bit of caching. Consider running with at least 8GB of memory.

Disks
^^^^^

This is a stateless process, disk performances are not relevant.

Network
^^^^^^^

Depending on your throughput, you might be better off running this with 10Gb NIC. In this scenario, you can easily achieves 350MBps of writes.


BookKeeper
~~~~~~~~~~

BookKeeper is the log segment store, which is a stateful service. There are two factors to measure the
capability of a Bookie instance: `bandwidth` and `storage`. The bandwidth is majorly dominated by the
outbound traffic from write proxy, which is `(Write Throughput) * (Replication Factor)`. The storage is
majorly dominated by the traffic and also `Retention Period`.

Calculating the capacity of BookKeeper (number of instances of bookies) is a bit more complicated than Write
Proxy. The total number of instances is the maximum number of the instances of bookies calculated using
`bandwidth` and `storage`.

::

    Number of bookies based on bandwidth = (Write Throughput) * (Replication Factor) / (Bookie Inbound Bandwidth)
    Number of bookies based on storage = (Write Throughput) * (Replication Factor) * (Replication Factor) / (Bookie disk space)
    Number of bookies = maximum((number of bookies based on bandwidth), (number of bookies based on storage))

We should consider both bandwidth and storage when choosing the hardware for bookies. There are several rules to follow:
- A bookie should have multiple disks.
- The number of disks used as journal disks should have similar I/O bandwidth as its *INBOUND* network bandwidth. For example, if you plan to use a disk for journal which I/O bandwidth is around 100MBps, a 1Gb NIC is a better choice than 10Gb NIC.
- The number of disks used as ledger disks should be large enough to hold data if retention period is typical long.

The cost estimation is straightforward based on the number of bookies estimated above.

::

    Cost of bookies = (Number of bookies) * (Bookie TCO)

Read Proxy
~~~~~~~~~~

Similar as Write Proxy, Read Proxy is also dominated by *OUTBOUND* bandwidth, which is reflected as incoming `Write Throughput` and `Fanout Factor`.

Calculating the capacity of Read Proxy (number of instances of read proxies) is also pretty straightforward.
The formula is listed as below.

::

    Number of Read Proxies = (Write Throughput) * (Fanout Factor) / (Read Proxy Outbound Bandwidth)

As it is bandwidth bound, we'd recommend using machines that have high network bandwith (e.g 10Gb NIC).

The cost estimation is also straightforward.

::

    Bandwidth TCO ($/day/MB) = (Read Proxy TCO) / (Read Proxy Outbound Bandwidth)
    Cost of read proxies = (Write Throughput) * (Fanout Factor) / (Bandwidth TCO)


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
