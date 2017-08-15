<!DOCTYPE html>
<html lang="en">

  <head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>API - Rewind reading records by time</title>
  <meta name="description" content="Apache DistributedLog is an high performance replicated log.
">

  <link rel="stylesheet" href="/distributedlog-staging-site/styles/site.css">
  <link rel="stylesheet" href="/distributedlog-staging-site/css/theme.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js"></script>
  <script src="/distributedlog-staging-site/js/bootstrap.min.js"></script>
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/latest/tutorials/basic-6.rst" data-proofer-ignore>
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
        .. contents:: Basic Tutorial - Rewind reading records by time

Rewind reading records by time
==============================

This tutorial shows how to rewind reading data from a stream by time.

.. sectnum::

Open a distributedlog manager
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Create distributedlog URI
-------------------------

::

        String dlUriStr = ...;
        URI uri = URI.create(dlUriStr);


Create distributedlog configuration
-----------------------------------

::

        DistributedLogConfiguration conf = new DistributedLogConfiguration();


Build the distributedlog namespace
----------------------------------

::

        DistributedLogNamespace namespace = DistributedLogNamespaceBuilder.newBuilder()
                .conf(conf)
                .uri(uri)
                .build(); 


Open the distributedlog manager
-------------------------------

::

        DistributedLogManager dlm = namespace.openLog("basic-stream-10");


Rewind the stream
~~~~~~~~~~~~~~~~~

Position the reader using timestamp
-----------------------------------

Since the records written by write proxy will be assigned `System.currentTimeMillis()`
as the `TransactionID`. It is straightforward to use `TransactionID` to rewind reading
the records.

::

        int rewindSeconds = 60; // 60 seconds
        long fromTxID = System.currentTimeMillis() -
                TimeUnit.MILLISECONDS.convert(rewindSeconds, TimeUnit.SECONDS);
        AsyncLogReader reader = FutureUtils.result(dlm.openAsyncLogReader(fromTxID));


Read Records
~~~~~~~~~~~~

Read the next available record from the stream. The future is satisified when the record is available.

::

        Future<LogRecordWithDLSN> readFuture = reader.readNext();


Register the read callback
---------------------------

Register a future listener on read completion. The reader will be notified once the record is ready for consuming.

::

        final FutureEventListener<LogRecordWithDLSN> readListener = new FutureEventListener<LogRecordWithDLSN>() {
            @Override
            public void onFailure(Throwable cause) {
                // executed when read failed.
            }

            @Override
            public void onSuccess(LogRecordWithDLSN record) {
                // process the record
                ...
                // issue read next
                reader.readNext().addEventListener(this);
            }
        };
        reader.readNext().addEventListener(readListener);


Close the reader
~~~~~~~~~~~~~~~~

Close the reader after usage.

::

        FutureUtils.result(reader.asyncClose());


Run the tutorial
~~~~~~~~~~~~~~~~

Run the example in the following steps:

Start the local bookkeeper cluster
----------------------------------

You can use follow command to start the distributedlog stack locally.
After the distributedlog cluster is started, you could access it using
distributedlog uri *distributedlog://127.0.0.1:7000/messaging/distributedlog*.

::

        // dlog local ${zk-port}
        ./distributedlog-core/bin/dlog local 7000


Start the write proxy
---------------------

Start the write proxy, listening on port 8000.

::

        // DistributedLogServerApp -p ${service-port} --shard-id ${shard-id} -sp ${stats-port} -u {distributedlog-uri} -mx -c ${conf-file}
        ./distributedlog-proxy-server/bin/dlog org.apache.distributedlog.service.DistributedLogServerApp -p 8000 --shard-id 1 -sp 8001 -u distributedlog://127.0.0.1:7000/messaging/distributedlog -mx -c ${distributedlog-repo}/distributedlog-proxy-server/conf/distributedlog_proxy.conf


Create the stream
-----------------

Create the stream under the distributedlog uri.

::

        // Create Stream `basic-stream-10`
        // dlog tool create -u ${distributedlog-uri} -r ${stream-prefix} -e ${stream-regex}
        ./distributedlog-core/bin/dlog tool create -u distributedlog://127.0.0.1:7000/messaging/distributedlog -r basic-stream- -e 10


Generate records
----------------

Run the `RecordGenerator` to generate records.

::

        // Write Records into Stream `basic-stream-10` in 1 requests/second
        // runner run org.apache.distributedlog.basic.RecordGenerator ${distributedlog-uri} ${stream} ${rate}
        ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.RecordGenerator 'inet!127.0.0.1:8000' basic-stream-10 1


Rewind the stream
-----------------

Rewind the stream using `StreamRewinder` to read records from 30 seconds ago

::

        // Rewind `basic-stream-10`
        // runner run org.apache.distributedlog.basic.StreamRewinder ${distributedlog-uri} ${stream} ${seconds-to-rewind}
        ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.StreamRewinder distributedlog://127.0.0.1:7000/messaging/distributedlog basic-stream-10  30


Check the results
-----------------

Example output from `StreamRewinder`.

::

        // Output of `StreamRewinder`
        Opening log stream basic-stream-10
        Record records starting from 1462736697481 which is 30 seconds ago
        Received record DLSN{logSegmentSequenceNo=1, entryId=264, slotId=0}
        """
        record-1462736697685
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=266, slotId=0}
        """
        record-1462736698684
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=268, slotId=0}
        """
        record-1462736699684
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=270, slotId=0}
        """
        record-1462736700686
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=272, slotId=0}
        """
        record-1462736701685
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=274, slotId=0}
        """
        record-1462736702684
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=276, slotId=0}
        """
        record-1462736703683
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=278, slotId=0}
        """
        record-1462736704685
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=280, slotId=0}
        """
        record-1462736705686
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=282, slotId=0}
        """
        record-1462736706682
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=284, slotId=0}
        """
        record-1462736707685
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=286, slotId=0}
        """
        record-1462736708686
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=288, slotId=0}
        """
        record-1462736709684
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=290, slotId=0}
        """
        record-1462736710684
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=292, slotId=0}
        """
        record-1462736711686
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=294, slotId=0}
        """
        record-1462736712686
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=296, slotId=0}
        """
        record-1462736713684
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=298, slotId=0}
        """
        record-1462736714682
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=300, slotId=0}
        """
        record-1462736715685
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=302, slotId=0}
        """
        record-1462736716684
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=304, slotId=0}
        """
        record-1462736717684
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=306, slotId=0}
        """
        record-1462736718684
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=308, slotId=0}
        """
        record-1462736719685
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=310, slotId=0}
        """
        record-1462736720683
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=312, slotId=0}
        """
        record-1462736721686
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=314, slotId=0}
        """
        record-1462736722685
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=316, slotId=0}
        """
        record-1462736723683
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=318, slotId=0}
        """
        record-1462736724683
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=320, slotId=0}
        """
        record-1462736725685
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=322, slotId=0}
        """
        record-1462736726686
        """
        Reader caught with latest data
        Received record DLSN{logSegmentSequenceNo=1, entryId=324, slotId=0}
        """
        record-1462736727686
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=326, slotId=0}
        """
        record-1462736728684
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=328, slotId=0}
        """
        record-1462736729682
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=330, slotId=0}
        """
        record-1462736730685
        """

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
