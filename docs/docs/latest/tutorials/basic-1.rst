<!DOCTYPE html>
<html lang="en">

  <head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>API - Write Records (via core library)</title>
  <meta name="description" content="Apache DistributedLog is an high performance replicated log.
">

  <link rel="stylesheet" href="/distributedlog-staging-site/styles/site.css">
  <link rel="stylesheet" href="/distributedlog-staging-site/css/theme.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js"></script>
  <script src="/distributedlog-staging-site/js/bootstrap.min.js"></script>
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/latest/tutorials/basic-1.rst" data-proofer-ignore>
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
        .. contents:: Basic Tutorial - Using Core Library to write records

Basic Tutorial - Write Records using Core Library
=================================================

This tutorial shows how to write records using core library.

.. sectnum::

Open a writer
~~~~~~~~~~~~~

Before everything, you have to open a writer to write records.
These are the steps to follow to `open a writer`.

Create distributedlog URI
-------------------------

::

    String dlUriStr = ...;
    URI uri = URI.create(dlUriStr);

Create distributedlog configuration
-----------------------------------

::

    DistributedLogConfiguration conf = new DistributedLogConfiguration();


Enable immediate flush
----------------------

::

    conf.setImmediateFlushEnabled(true);
    conf.setOutputBufferSize(0);
    conf.setPeriodicFlushFrequencyMilliSeconds(0);


Enable immediate locking
------------------------

So if there is already a writer wring to the stream, opening another writer will
fail because previous writer already held a lock.

::

    conf.setLockTimeout(DistributedLogConstants.LOCK_IMMEDIATE);


Build the distributedlog namespace
----------------------------------

::

    DistributedLogNamespace namespace = DistributedLogNamespaceBuilder.newBuilder()
            .conf(conf)
            .uri(uri)
            .regionId(DistributedLogConstants.LOCAL_REGION_ID)
            .clientId("console-writer")
            .build(); 


Open the writer
---------------

::

    DistributedLogManager dlm = namespace.openLog("basic-stream-1");
    AsyncLogWriter writer = FutureUtils.result(dlm.openAsyncLogWriter());


Write Records
~~~~~~~~~~~~~

Once you got a `writer` instance, you can start writing `records` into the stream.

Construct a log record
----------------------

Here lets use `System.currentTimeMillis()` as the `TransactionID`.

::

    byte[] data = ...;
    LogRecord record = new LogRecord(System.currentTimeMillis(), data); 


Write the log record
--------------------

::

    Future<DLSN> writeFuture = writer.write(record);


Register the write callback
---------------------------

Register a future listener on write completion. The writer will be notified once the write is completed.

::

    writeFuture.addEventListener(new FutureEventListener<DLSN>() {
        @Override
        public void onFailure(Throwable cause) {
            // executed when write failed.
        }

        @Override
        public void onSuccess(DLSN value) {
            // executed when write completed.
        }
    });


Close the writer
~~~~~~~~~~~~~~~~

Close the writer after usage
----------------------------

::

    FutureUtils.result(writer.asyncClose());


Run the tutorial
~~~~~~~~~~~~~~~~

Run the example in the following steps:

Start the local bookkeeper cluster
----------------------------------

You can use follow command to start the distributedlog stack locally.
After the distributedlog is started, you could access it using
distributedlog uri *distributedlog://127.0.0.1:7000/messaging/distributedlog*.

::

        // dlog local ${zk-port}
        ./distributedlog-core/bin/dlog local 7000


Create the stream
-----------------

::

        // Create Stream `basic-stream-1`
        // dlog tool create -u ${distributedlog-uri} -r ${stream-prefix} -e ${stream-regex}
        ./distributedlog-core/bin/dlog tool create -u distributedlog://127.0.0.1:7000/messaging/distributedlog -r basic-stream- -e 1


Tail the stream
---------------

Tailing the stream using `TailReader` to wait for new records.

::

        // Tailing Stream `basic-stream-1`
        // runner run org.apache.distributedlog.basic.TailReader ${distributedlog-uri} ${stream}
        ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.TailReader distributedlog://127.0.0.1:7000/messaging/distributedlog basic-stream-1


Write records
-------------

Run the example to write records to the stream in a console.

::

        // Write Records into Stream `basic-stream-1`
        // runner run org.apache.distributedlog.basic.ConsoleWriter ${distributedlog-uri} ${stream}
        ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.ConsoleWriter distributedlog://127.0.0.1:7000/messaging/distributedlog basic-stream-1


Check the results
-----------------

Example output from `ConsoleWriter` and `TailReader`.

::

        // Output of `ConsoleWriter`
        Opening log stream basic-stream-1
        [dlog] > test!
        [dlog] >


        // Output of `TailReader`
        Opening log stream basic-stream-1
        Log stream basic-stream-1 is empty.
        Wait for records starting from DLSN{logSegmentSequenceNo=1, entryId=0, slotId=0}
        Received record DLSN{logSegmentSequenceNo=1, entryId=0, slotId=0}
        """
        test!
        """

Attempt a second writer 
-----------------------

Open another terminal to run `ConsoleWriter`. It would fail with `OwnershipAcquireFailedException` as previous
`ConsoleWriter` is still holding lock on writing to stream `basic-stream-1`.

::

        Opening log stream basic-stream-1
        Exception in thread "main" org.apache.distributedlog.exceptions.OwnershipAcquireFailedException: LockPath - /messaging/distributedlog/basic-stream-1/<default>/lock: Lock acquisition failed, the current owner is console-writer
            at org.apache.distributedlog.lock.ZKSessionLock$8.apply(ZKSessionLock.java:570)
            at org.apache.distributedlog.lock.ZKSessionLock$8.apply(ZKSessionLock.java:567)
            at com.twitter.util.Future$$anonfun$map$1$$anonfun$apply$8.apply(Future.scala:1041)
            at com.twitter.util.Try$.apply(Try.scala:13)
            at com.twitter.util.Future$.apply(Future.scala:132)
            at com.twitter.util.Future$$anonfun$map$1.apply(Future.scala:1041)
            at com.twitter.util.Future$$anonfun$map$1.apply(Future.scala:1040)
            at com.twitter.util.Promise$Transformer.liftedTree1$1(Promise.scala:112)
            at com.twitter.util.Promise$Transformer.k(Promise.scala:112)
            at com.twitter.util.Promise$Transformer.apply(Promise.scala:122)
            at com.twitter.util.Promise$Transformer.apply(Promise.scala:103)
            at com.twitter.util.Promise$$anon$1.run(Promise.scala:357)
            at com.twitter.concurrent.LocalScheduler$Activation.run(Scheduler.scala:178)
            at com.twitter.concurrent.LocalScheduler$Activation.submit(Scheduler.scala:136)
            at com.twitter.concurrent.LocalScheduler.submit(Scheduler.scala:207)
            at com.twitter.concurrent.Scheduler$.submit(Scheduler.scala:92)
            at com.twitter.util.Promise.runq(Promise.scala:350)
            at com.twitter.util.Promise.updateIfEmpty(Promise.scala:716)
            at com.twitter.util.Promise.update(Promise.scala:694)
            at com.twitter.util.Promise.setValue(Promise.scala:670)
            at org.apache.distributedlog.lock.ZKSessionLock$9.safeRun(ZKSessionLock.java:622)
            at org.apache.bookkeeper.util.SafeRunnable.run(SafeRunnable.java:31)
            at java.util.concurrent.Executors$RunnableAdapter.call(Executors.java:471)
            at java.util.concurrent.FutureTask.run(FutureTask.java:262)
            at java.util.concurrent.ScheduledThreadPoolExecutor$ScheduledFutureTask.access$201(ScheduledThreadPoolExecutor.java:178)
            at java.util.concurrent.ScheduledThreadPoolExecutor$ScheduledFutureTask.run(ScheduledThreadPoolExecutor.java:292)
            at java.util.concurrent.ThreadPoolExecutor.runWorker(ThreadPoolExecutor.java:1145)
            at java.util.concurrent.ThreadPoolExecutor$Worker.run(ThreadPoolExecutor.java:615)
            at java.lang.Thread.run(Thread.java:745) 

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
