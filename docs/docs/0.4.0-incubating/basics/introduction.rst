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
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/0.4.0-incubating/basics/introduction.rst" data-proofer-ignore>
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
        .. contents:: DistributedLog Overview

Introduction
============

DistributedLog (DL) is a high performance replicated log service.
It offers durability, replication and strong consistency, which provides a fundamental building block
for building reliable distributed systems, e.g replicated-state-machines, general pub/sub systems,
distributed databases, distributed queues and etc.

DistributedLog maintains sequences of records in categories called *Logs* (aka *Log Streams*).
The processes that write records to a DL log are *writers*, while the processes that read
from logs and process the records are *readers*.


.. figure:: ../images/softwarestack.png
   :align: center

   Figure 1. DistributedLog Software Stack

Logs
----

A **log** is an ordered, immutable sequence of *log records*.

.. figure:: ../images/datamodel.png
   :align: center

   Figure 2. Anatomy of a log stream

Log Records
~~~~~~~~~~~

Each **log record** is a sequence of bytes.
**Log records** are written sequentially into a *log stream*, and will be assigned with
a unique sequence number *called* **DLSN** (DistributedLog Sequence Number). Besides *DLSN*,
applications could assign its own sequence number while constructing log records. The
application defined sequence number is called **TransactionID** (*txid*). Either *DLSN*
or *TransactionID* could be used for positioning readers to start reading from a specific
*log record*.

Log Segments
~~~~~~~~~~~~

A **log** is broken down into *segments*, which each log segment contains its subset of
records. **Log segments** are distributed and stored in a log segment store (e.g Apache BookKeeper).
DistributedLog rolls the log segments based on configured rolling policy - either a configurable
period of time (e.g. every 2 hours) or a configurable maximum size (e.g. every 128MB).
So the data of logs will be divided into equal-sized *log segments* and distributed evenly
across log segment storage nodes. It allows the log to scale beyond a size that will fit on
a single server and also spread read traffic among the cluster.

The data of logs will either be kept forever until application *explicitly* truncates or be retained
for a configurable period of time. **Explicit Truncation** is useful for building replicated
state machines such as distributed databases. They usually require strong controls over when
the data could be truncated. **Time-based Retention** is useful for real-time analytics. They only
care about the data within a period of time.

Namespaces
~~~~~~~~~~

The *log streams* belong to same organization are usually categorized and managed under
a **namespace**. A DL **namespace** is basically for applications to locate where the
*log streams* are. Applications could *create* and *delete* streams under a namespace,
and also be able to *truncate* a stream to given sequence number (either *DLSN* or *TransactionID*).

Writers
-------

Writers write data into the logs of their choice. All the records are
appended into the logs in order. The sequencing is done by the writer,
which means there is only one active writer for a log at a given time.
DL guarantees correctness when two writers attempt writing to
to a same log when network partition happens - via fencing mechanism
in log segment store.

The log writers are served and managed in a service tier called *Write Proxy*.
The *Write Proxy* is used for accepting fan-in writes from large number
of clients. Details on **Fan-in and Fan-out** can be found further into this doc.

Readers
-------

Readers read records from the logs of their choice, starting from a provided
position. The provided position could be either *DLSN* or *TransactionID*.
The readers will read records in strict order from the logs. Different readers
could read records starting from different positions in a same log.

Unlike other pub/sub systems, DistributedLog doesn't record/manage readers' positions.
It leaves the tracking responsibility to applications, as different applications
might have different requirements on tracking and coordinating positions. It is hard
to get it right with a single approach. For example, distributed databases might store
the reader positions along with SSTables, so they would resume applying transactions
from the positions stored in SSTables. Tracking reader positions could easily be done
in application level using various stores (e.g. ZooKeeper, file system, or key/value stores).

The log records could be cached in a service tier called *Read Proxy*, to serve
a large number of readers.

Fan-in and Fan-out
------------------

The core of DistributedLog supports single-writer, multiple-readers semantics. The service layer
built on top of the *DistributedLog Core* to support large scale of number of writers and readers.
The service layer includes **Write Proxy** and **Read Proxy**. **Write Proxy** manages
the writers of logs and fail over them when machines are failed. It allows supporting
which don't care about the log ownership by aggregating writes from many sources (aka *Fan-in*).
**Read Proxy** optimize reader path by caching log records in cases where hundreds or
thousands of readers are consuming a same log stream.

Guarantees
----------

At a high level, DistributedLog gives the following guarantees:

* Records written by a writer to a log will be appended in the order they are written. That is, if a record *R1* is written by same writer as a record *R2*, *R1* will have a smaller sequence number than *R2*.
* Readers see records in the same order they were written to the log.
* All records are persisted on disk before acknowledgments, to gurantee durability.
* For a log with replication factor of N, DistributedLog tolerates up to N-1 server failures without losing any records.

More details on these guarantees are given in the [design section](http://bookkeeper.apache.org/distributedlog/docs/0.4.0-incubating/user_guide/design/main.html).


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
