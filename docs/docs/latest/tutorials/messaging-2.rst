<!DOCTYPE html>
<html lang="en">

  <head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>Tutorials - Write records to multiple streams using a load balancer</title>
  <meta name="description" content="Apache DistributedLog is an high performance replicated log.
">

  <link rel="stylesheet" href="/distributedlog-staging-site/styles/site.css">
  <link rel="stylesheet" href="/distributedlog-staging-site/css/theme.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js"></script>
  <script src="/distributedlog-staging-site/js/bootstrap.min.js"></script>
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/latest/tutorials/messaging-2.rst" data-proofer-ignore>
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
        .. contents:: Messaging Tutorial - Write records to multiple streams using a load balancer

How to write records to multiple streams using a load balancer
==============================================================

If applications does not care about ordering and they just want use multiple streams to transform messages, it is easier
to use a load balancer to balancing the writes among the multiple streams.

This tutorial shows how to build a multi-streams writer, which ues a finagle load balancer to balancing traffic among multiple streams.

.. sectnum::

Make writing to a stream as a finagle service
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

In order to leverage the finagle load balancer to balancing traffic among multiple streams, we have to make writing
to a stream as a finagle service.

::

    class StreamWriter<VALUE> extends Service<VALUE, DLSN> {

        private final String stream;
        private final DistributedLogClient client;

        StreamWriter(String stream,
                     DistributedLogClient client) {
            this.stream = stream;
            this.client = client;
        }

        @Override
        public Future<DLSN> apply(VALUE request) {
            return client.write(stream, ByteBuffer.wrap(request.toString().getBytes(UTF_8)));
        }
    } 


Create a load balancer from multiple streams
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Create a ServiceFactory
-----------------------

Create a set of finagle `ServiceFactory` over multiple streams.

::

        String[] streams;
        Set<ServiceFactory<VALUE, DLSN>> serviceFactories = Sets.newHashSet();
        for (String stream : streams) {
            Service<VALUE, DLSN> service = new StreamWriter(stream, client);
            serviceFactories.add(new SingletonFactory<VALUE, DLSN>(service));
        }


Create the load balancer
------------------------

::

        Service<VALUE, DLSN> writeSerivce =
            Balancers.heap(new scala.util.Random(System.currentTimeMillis()))
                .newBalancer(
                        Activity.value(scalaSet),
                        NullStatsReceiver.get(),
                        new NoBrokersAvailableException("No partitions available")
                ).toService();


Write records
~~~~~~~~~~~~~

Once the balancer service is initialized, we can write records through the balancer service.

::

    Future<DLSN> writeFuture = writeSerivce.write(...);


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

        // Create Stream `messaging-stream-{1,5}`
        // dlog tool create -u ${distributedlog-uri} -r ${stream-prefix} -e ${stream-regex}
        ./distributedlog-core/bin/dlog tool create -u distributedlog://127.0.0.1:7000/messaging/distributedlog -r messaging-stream- -e 1-5


Tail the streams
----------------

Tailing the streams using `MultiReader` to wait for new records.

::

        // Tailing Stream `messaging-stream-{1,5}`
        // runner run org.apache.distributedlog.basic.MultiReader ${distributedlog-uri} ${stream}[, ${stream}]
        ./distributedlog-tutorials/distributedlog-basic/bin/runner run org.apache.distributedlog.basic.MultiReader distributedlog://127.0.0.1:7000/messaging/distributedlog messaging-stream-1,messaging-stream-2,messaging-stream-3,messaging-stream-4,messaging-stream-5


Write records
-------------

Run the example to write records to multiple stream in a console.

::

        // Write Records into Stream `messaging-stream-{1,5}`
        // runner run org.apache.distributedlog.messaging.ConsoleProxyRRMultiWriter ${distributedlog-uri} ${stream}[, ${stream}]
        ./distributedlog-tutorials/distributedlog-messaging/bin/runner run org.apache.distributedlog.messaging.ConsoleProxyRRMultiWriter 'inet!127.0.0.1:8000' messaging-stream-1,messaging-stream-2,messaging-stream-3,messaging-stream-4,messaging-stream-5


Check the results
-----------------

Example output from `ConsoleProxyRRMultiWriter` and `MultiReader`.

::

        // Output of `ConsoleProxyRRMultiWriter`
        Picked up JAVA_TOOL_OPTIONS: -Dfile.encoding=utf8
        May 08, 2016 1:22:35 PM com.twitter.finagle.BaseResolver$$anonfun$resolvers$1 apply
        INFO: Resolver[inet] = com.twitter.finagle.InetResolver(com.twitter.finagle.InetResolver@6c4cbf96)
        May 08, 2016 1:22:35 PM com.twitter.finagle.BaseResolver$$anonfun$resolvers$1 apply
        INFO: Resolver[fixedinet] = com.twitter.finagle.FixedInetResolver(com.twitter.finagle.FixedInetResolver@57052dc3)
        May 08, 2016 1:22:35 PM com.twitter.finagle.BaseResolver$$anonfun$resolvers$1 apply
        INFO: Resolver[neg] = com.twitter.finagle.NegResolver$(com.twitter.finagle.NegResolver$@14ff89d7)
        May 08, 2016 1:22:35 PM com.twitter.finagle.BaseResolver$$anonfun$resolvers$1 apply
        INFO: Resolver[nil] = com.twitter.finagle.NilResolver$(com.twitter.finagle.NilResolver$@14b28d06)
        May 08, 2016 1:22:35 PM com.twitter.finagle.BaseResolver$$anonfun$resolvers$1 apply
        INFO: Resolver[fail] = com.twitter.finagle.FailResolver$(com.twitter.finagle.FailResolver$@56488f87)
        May 08, 2016 1:22:35 PM com.twitter.finagle.Init$$anonfun$1 apply$mcV$sp
        INFO: Finagle version media-platform-tools/release-20160330-1117-sgerstein-9-g2dcdd6c (rev=2dcdd6c866f9bd3599ed49568d651189735e8ad6) built at 20160330-160058
        [dlog] > message-1
        [dlog] > message-2
        [dlog] > message-3
        [dlog] > message-4
        [dlog] > message-5
        [dlog] >


        // Output of `MultiReader`
        Opening log stream messaging-stream-1
        Opening log stream messaging-stream-2
        Opening log stream messaging-stream-3
        Opening log stream messaging-stream-4
        Opening log stream messaging-stream-5
        Log stream messaging-stream-2 is empty.
        Wait for records from messaging-stream-2 starting from DLSN{logSegmentSequenceNo=1, entryId=0, slotId=0}
        Open reader to read records from stream messaging-stream-2
        Log stream messaging-stream-1 is empty.
        Wait for records from messaging-stream-1 starting from DLSN{logSegmentSequenceNo=1, entryId=0, slotId=0}
        Open reader to read records from stream messaging-stream-1
        Log stream messaging-stream-3 is empty.
        Wait for records from messaging-stream-3 starting from DLSN{logSegmentSequenceNo=1, entryId=0, slotId=0}
        Open reader to read records from stream messaging-stream-3
        Log stream messaging-stream-4 is empty.
        Wait for records from messaging-stream-4 starting from DLSN{logSegmentSequenceNo=1, entryId=0, slotId=0}
        Open reader to read records from stream messaging-stream-4
        Log stream messaging-stream-5 is empty.
        Wait for records from messaging-stream-5 starting from DLSN{logSegmentSequenceNo=1, entryId=0, slotId=0}
        Open reader to read records from stream messaging-stream-5
        Received record DLSN{logSegmentSequenceNo=1, entryId=2, slotId=0} from stream messaging-stream-3
        """
        message-1
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=2, slotId=0} from stream messaging-stream-2
        """
        message-2
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=4, slotId=0} from stream messaging-stream-2
        """
        message-3
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=2, slotId=0} from stream messaging-stream-4
        """
        message-4
        """
        Received record DLSN{logSegmentSequenceNo=1, entryId=6, slotId=0} from stream messaging-stream-2
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
