<!DOCTYPE html>
<html lang="en">

  <head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>API - Atomic Write Multiple Records</title>
  <meta name="description" content="Apache DistributedLog is an high performance replicated log.
">

  <link rel="stylesheet" href="/distributedlog-staging-site/styles/site.css">
  <link rel="stylesheet" href="/distributedlog-staging-site/css/theme.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js"></script>
  <script src="/distributedlog-staging-site/js/bootstrap.min.js"></script>
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/latest/tutorials/basic-4.rst" data-proofer-ignore>
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
        .. contents:: Basic Tutorial - Write Multi Records Atomic using Write Proxy Client

Write Multi Records Atomic using Write Proxy Client
===================================================

This tutorial shows how to write multi records atomic using write proxy client.

.. sectnum::

Open a write proxy client
~~~~~~~~~~~~~~~~~~~~~~~~~

Create write proxy client builder
---------------------------------

::

        DistributedLogClientBuilder builder = DistributedLogClientBuilder.newBuilder();
                .clientId(ClientId.apply("atomic-writer"))
                .name("atomic-writer");


Enable thrift mux
-----------------

::

        builder = builder.thriftmux(true);


Point the client to write proxy using finagle name
--------------------------------------------------

::

        String finagleNameStr = "inet!127.0.0.1:8000";
        builder = builder.finagleNameStr(finagleNameStr);


Build the write proxy client
----------------------------

::

        DistributedLogClient client = builder.build();


Write Records
~~~~~~~~~~~~~

Create a RecordSet
------------------

Create a `RecordSet` for multiple records. The RecordSet has initial `16KB` buffer and its
compression codec is `NONE`.

::

        LogRecordSet.Writer recordSetWriter = LogRecordSet.newWriter(16 * 1024, Type.NONE);


Write multiple records
----------------------

Write multiple records into the `RecordSet`.

::

        for (String msg : messages) {
            ByteBuffer msgBuf = ByteBuffer.wrap(msg.getBytes(UTF_8));
            Promise<DLSN> writeFuture = new Promise<DLSN>();
            recordSetWriter.writeRecord(msgBuf, writeFuture);
        }


Write the RecordSet
-------------------

Write the `RecordSet` to a stream.

::

        String streamName = "basic-stream-8";
        Future<DLSN> writeFuture = client.writeRecordSet(streamName, recordSetWriter);


Register the write callback
---------------------------

Register a future listener on write completion. The writer will be notified once the write is completed.

::

        writeFuture.addEventListener(new FutureEventListener<DLSN>() {
            @Override
            public void onFailure(Throwable cause) {
                // executed when write failed.
                recordSetWriter.abortTransmit(cause);
            }

            @Override
            public void onSuccess(DLSN value) {
                // executed when write completed.
                recordSetWriter.completeTransmit(
                        dlsn.getLogSegmentSequenceNo(),
                        dlsn.getEntryId(),
                        dlsn.getSlotId());
            }
        });


Close the write proxy client
~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Close the write proxy client after usage.

::

        client.close();


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

        // Create Stream `basic-stream-8`
        // dlog tool create -u ${distributedlog-uri} -r ${stream-prefix} -e ${stream-regex}
        ./distributedlog-core/bin/dlog tool create -u distributedlog://127.0.0.1:7000/messaging/distributedlog -r basic-stream- -e 8


Tail the stream
---------------

Tailing the stream using `TailReader` to wait for new records.

::

        // Tailing Stream `basic-stream-8`
        // runner run org.apache.distributedlog.basic.TailReader ${distributedlog-uri} ${stream}
        ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.TailReader distributedlog://127.0.0.1:7000/messaging/distributedlog basic-stream-8


Write records
-------------

Run the example to write multiple records to the stream.

::

        // Write Records into Stream `basic-stream-8`
        // runner run org.apache.distributedlog.basic.AtomicWriter ${distributedlog-uri} ${stream} ${message}[, ${message}]
        ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.AtomicWriter 'inet!127.0.0.1:8000' basic-stream-8 "message-1" "message-2" "message-3" "message-4" "message-5"


Check the results
-----------------

Example output from `AtomicWriter` and `TailReader`.

::

        // Output of `AtomicWriter`
        May 08, 2016 11:48:19 AM com.twitter.finagle.BaseResolver$$anonfun$resolvers$1 apply
        INFO: Resolver[inet] = com.twitter.finagle.InetResolver(com.twitter.finagle.InetResolver@6c3e459e)
        May 08, 2016 11:48:19 AM com.twitter.finagle.BaseResolver$$anonfun$resolvers$1 apply
        INFO: Resolver[fixedinet] = com.twitter.finagle.FixedInetResolver(com.twitter.finagle.FixedInetResolver@4d5698f)
        May 08, 2016 11:48:19 AM com.twitter.finagle.BaseResolver$$anonfun$resolvers$1 apply
        INFO: Resolver[neg] = com.twitter.finagle.NegResolver$(com.twitter.finagle.NegResolver$@57052dc3)
        May 08, 2016 11:48:19 AM com.twitter.finagle.BaseResolver$$anonfun$resolvers$1 apply
        INFO: Resolver[nil] = com.twitter.finagle.NilResolver$(com.twitter.finagle.NilResolver$@14ff89d7)
        May 08, 2016 11:48:19 AM com.twitter.finagle.BaseResolver$$anonfun$resolvers$1 apply
        INFO: Resolver[fail] = com.twitter.finagle.FailResolver$(com.twitter.finagle.FailResolver$@14b28d06)
        May 08, 2016 11:48:19 AM com.twitter.finagle.Init$$anonfun$1 apply$mcV$sp
        Write 'message-1' as record DLSN{logSegmentSequenceNo=1, entryId=0, slotId=0}
        Write 'message-2' as record DLSN{logSegmentSequenceNo=1, entryId=0, slotId=1}
        Write 'message-3' as record DLSN{logSegmentSequenceNo=1, entryId=0, slotId=2}
        Write 'message-4' as record DLSN{logSegmentSequenceNo=1, entryId=0, slotId=3}
        Write 'message-5' as record DLSN{logSegmentSequenceNo=1, entryId=0, slotId=4}


        // Output of `TailReader`
        Opening log stream basic-stream-8
        Log stream basic-stream-8 is empty.
        Wait for records starting from DLSN{logSegmentSequenceNo=1, entryId=0, slotId=0}
        Received record DLSN{logSegmentSequenceNo=1, entryId=0, slotId=0}
        """
        message-1
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=0, slotId=1}
        """
        message-2
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=0, slotId=2}
        """
        message-3
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=0, slotId=3}
        """
        message-4
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=0, slotId=4}
        """
        message-5
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
