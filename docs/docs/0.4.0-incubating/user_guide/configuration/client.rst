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
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/0.4.0-incubating/user_guide/configuration/client.rst" data-proofer-ignore>
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
        .. contents:: Client Configuration

Client Configuration
====================

This section describes the settings used by DistributedLog Write Proxy Client.

Different from core library, the proxy client uses a builder to configure its settings.

::

    DistributedLogClient client = DistributedLogClientBuilder.newBuilder()
        .name("test-client")
        .clientId("test-client-id")
        .finagleNameStr("inet!localhost:8080")
        .statsReceiver(statsReceiver)
        .build();

Client Builder Settings
-----------------------

Common Settings
~~~~~~~~~~~~~~~

- *name(string)*: The name of the distributedlog client.
- *clientId(string)*: The client id used for the underneath finagle client. It is a string identifier that server will
  use to identify who are the client. So the server can book keep and optionally reject unknown clients.
- *requestTimeoutMs(int)*: The maximum time that a request could take before claiming it as failure, in milliseconds.
- *thriftmux(boolean)*: The flag to enable or disable using ThriftMux_ on the underneath channels.
- *streamFailfast(boolean)*: The flag to enable or disable failfast the requests when the server responds `stream-not-ready`.
  A stream would be treated as not ready when it is initializing or rolling log segments. The setting is only take effects
  when the write proxy also enables `failFastOnStreamNotReady`.

.. _ThriftMux: http://twitter.github.io/finagle/guide/Protocols.html#mux

Environment Settings
~~~~~~~~~~~~~~~~~~~~

DistributedLog uses finagle Names_ to identify the network locations of write proxies.
Names must be supplied when building a distributedlog client through `finagleNameStr` or
`finagleNameStrs`.

.. _Names: http://twitter.github.io/finagle/guide/Names.html

- *finagleNameStr(string)*: The finagle name to locate write proxies.
- *finagleNameStrs(string, string...)*: A list of finagle names. It is typically used by the global replicated log wherever there
  are multiple regions of write proxies. The first parameter is the finagle name of local region; while the remaining parameters
  are the finagle names for remote regions.

Redirection Settings
~~~~~~~~~~~~~~~~~~~~

DistributedLog client can redirect the requests to other write proxies when accessing a write proxy doesn't own the given stream.
This section describes the settings related to redirection.

- *redirectBackoffStartMs(int)*: The initial backoff for redirection, in milliseconds.
- *redirectBackoffMaxMs(int)*: The maximum backoff for redirection, in milliseconds.
- *maxRedirects(int)*: The maximum number of redirections that a request could take before claiming it as failure.

Channel Settings
~~~~~~~~~~~~~~~~

DistributedLog client uses FinagleClient_ to establish the connections to the write proxy. A finagle client will be
created via ClientBuilder_ for each write proxy.

.. _FinagleClient: https://twitter.github.io/finagle/guide/Clients.html

.. _ClientBuilder: http://twitter.github.io/finagle/docs/index.html#com.twitter.finagle.builder.ClientBuilder

- *clientBuilder(ClientBuilder)*: The finagle client builder to build connection to each write proxy.

Ownership Cache Settings
~~~~~~~~~~~~~~~~~~~~~~~~

DistributedLog client maintains a ownership cache locally to archieve stable deterministic request routing. Normally,
the ownership cache is propagated after identified a new owner when performing stream related operations such as write.
The client also does handshaking when initiating connections to a write proxy or periodically for fast failure detection.
During handshaking, the client also pull the latest ownership mapping from write proxies to update its local cache, which
it would help detecting ownership changes quickly, and avoid latency penalty introduced by redirection when ownership changes.

- *handshakeWithClientInfo(boolean)*: The flag to enable or disable pulling ownership mapping during handshaking.
- *periodicHandshakeIntervalMs(long)*: The periodic handshake interval in milliseconds. Every provided interval, the DL client
  will handshake with existing proxies. It would detect proxy failures during handshaking. If the interval is already greater than
  `periodicOwnershipSyncIntervalMs`, the handshake will pull the latest ownership mapping. Otherwise, it will not. The default
  value is 5 minutes. Setting it to 0 or negative number will disable this feature.
- *periodicOwnershipSyncIntervalMs(long)*: The periodic ownership sync interval, in milliseconds. If periodic handshake is
  enabled, the handshake will sync ownership if the elapsed time is greater than the sync interval.
- *streamNameRegex(string)*: The regex to match the stream names that the client cares about their ownerships.

Constraint Settings
~~~~~~~~~~~~~~~~~~~

- *checksum(boolean)*: The flag to enable/disable checksum validation on requests that sent to proxy.

Stats Settings
~~~~~~~~~~~~~~

- *statsReceiver(StatsReceiver)*: The stats receiver used for collecting stats exposed by this client.
- *streamStatsReceiver(StatsReceiver)*: The stats receiver used for collecting per stream stats exposed by this client.

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
