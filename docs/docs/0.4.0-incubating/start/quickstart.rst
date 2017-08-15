<!DOCTYPE html>
<html lang="en">

  <head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>Setup &amp; Run Example</title>
  <meta name="description" content="Apache DistributedLog is an high performance replicated log.
">

  <link rel="stylesheet" href="/distributedlog-staging-site/styles/site.css">
  <link rel="stylesheet" href="/distributedlog-staging-site/css/theme.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js"></script>
  <script src="/distributedlog-staging-site/js/bootstrap.min.js"></script>
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/0.4.0-incubating/start/quickstart.rst" data-proofer-ignore>
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
        .. contents:: Get a DistributedLog cluster up running locally and run the example program in a few simple steps.

Quick Start
===========

This tutorial assumes you are starting from fresh and have no existing BookKeeper or ZooKeeper data.
If you already have an existing BookKeeper or ZooKeeper cluster, you can checkout the deploy_ section
for more details on how to deploy a production cluster.

.. _deploy: ../deployment/cluster

Step 1: Download the binary
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Download_ the stable version of `DistributedLog` and un-zip it.

.. _Download: ./download

::

    // Download the binary `distributedlog-all-${gitsha}.zip`
    > unzip distributedlog-all-${gitsha}.zip


Step 2: Start ZooKeeper & BookKeeper
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

DistributedLog uses `ZooKeeper` as the metadata store and `BookKeeper` as the log segment store. So
you need to first start a zookeeper server and a few bookies if you don't already have one. You can
use the `dlog` script in `distributedlog-service` package to get a standalone bookkeeper sandbox. It
starts a zookeeper server and `N` bookies (N is 3 by default).

::

    // Start the local sandbox instance at port `7000`
    > ./distributedlog-service/bin/dlog local 7000
    DistributedLog Sandbox is running now. You could access distributedlog://127.0.0.1:7000


Step 3: Create a DistributedLog namespace
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Before using distributedlog, you need to create a distributedlog namespace to store your own list of
streams. The zkServer for the local sandbox is `127.0.0.1:7000` and the bookkeeper's ledgers path is
`/ledgers`. You could create a namespace pointing to the corresponding bookkeeper cluster.

::

    > ./distributedlog-service/bin/dlog admin bind -l /ledgers -s 127.0.0.1:7000 -c distributedlog://127.0.0.1:7000/messaging/my_namespace
    No bookkeeper is bound to distributedlog://127.0.0.1:7000/messaging/my_namespace
    Created binding on distributedlog://127.0.0.1:7000/messaging/my_namespace.


If you don't want to create a separated namespace, you could use the default namespace `distributedlog://127.0.0.1:7000/messaging/distributedlog`.


Step 4: Create some log streams
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Let's create 5 log streams, prefixed with `messaging-stream-`.

::

    > ./distributedlog-service/bin/dlog tool create -u distributedlog://127.0.0.1:7000/messaging/my_namespace -r messaging-stream- -e 1-5


We can now see the streams if we run the `list` command from the tool.

::
    
    > ./distributedlog-service/bin/dlog tool list -u distributedlog://127.0.0.1:7000/messaging/my_namespace
    Streams under distributedlog://127.0.0.1:7000/messaging/my_namespace :
    --------------------------------
    messaging-stream-1
    messaging-stream-3
    messaging-stream-2
    messaging-stream-4
    messaging-stream-5
    --------------------------------


Step 5: Start a write proxy
~~~~~~~~~~~~~~~~~~~~~~~~~~~

Now, lets start a write proxy server that serves writes to distributedlog namespace `distributedlog://127.0.0.1/messaging/my_namespace`. The server listens on 8000 to accept fan-in write requests.

::
    
    > ./distributedlog-service/bin/dlog-daemon.sh start writeproxy -p 8000 --shard-id 1 -sp 8001 -u distributedlog://127.0.0.1:7000/messaging/my_namespace -mx -c `pwd`/distributedlog-service/conf/distributedlog_proxy.conf

From 0.3.51-RC1 and onwards, use the below command to start the write proxy

::

   > WP_SHARD_ID=1 WP_SERVICE_PORT=8000 WP_STATS_PORT=8001 WP_NAMESPACE='distributedlog://127.0.0.1:7000/messaging/my_namespace' ./distributedlog-service/bin/dlog-daemon.sh start writeproxy

Step 6: Tail reading records
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The distributedlog tutorial has a multi-streams reader that will dump out received records to standard output.

::
    
    > ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.MultiReader distributedlog://127.0.0.1:7000/messaging/my_namespace messaging-stream-1,messaging-stream-2,messaging-stream-3,messaging-stream-4,messaging-stream-5


Step 7: Write some records
~~~~~~~~~~~~~~~~~~~~~~~~~~

The distributedlog tutorial also has a multi-streams writer that will take input from a console and write it out
as records to the distributedlog write proxy. Each line will be sent as a separate record.

Run the writer and type a few lines into the console to send to the server.

::
    
    > ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.ConsoleProxyMultiWriter 'inet!127.0.0.1:8000' messaging-stream-1,messaging-stream-2,messaging-stream-3,messaging-stream-4,messaging-stream-5

If you have each of the above commands running in a different terminal then you should now be able to type messages into the writer terminal and see them appear in the reader terminal.

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
