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
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/0.4.0-incubating/user_guide/configuration/proxy.rst" data-proofer-ignore>
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
        .. contents:: Write Proxy Configuration

Write Proxy Configuration
=========================

This section describes the configuration settings used by DistributedLog Write Proxy.

All the server related settings are managed in `ServerConfiguration`. Similar as `DistributedLogConfiguration`,
it is also a properties based configuration, which extends from Apache commons `CompositeConfiguration`. All
server related settings are in lower case and use `'_'` to concat words. For example, `server_region_id` means
the region id used by the write proxy server.

Server Configuration Settings
-----------------------------

- *server_dlsn_version*: The version of serialized format of DLSN. The default value is 1. It is not recommended to change it.
- *server_region_id*: The region id used by the server to instantiate a DL namespace. The default value is `LOCAL`.
- *server_port*: The listen port of the write proxy. The default value is 0.
- *server_shard*: The shard id used by the server to identify itself. It is optional but recommended to set. For example, if
  the write proxy is running in `Apache Aurora`, you could use the instance id as the shard id. The default value is -1 (unset).
- *server_threads*: The number of threads for the executor of this server. The default value is the available processors.
- *server_enable_perstream_stat*: The flag to enable per stream stat in write proxy. It is different from `enablePerStreamStat`
  in core library. The setting here is controlling exposing the per stream stat exposed by write proxy, while `enablePerStreamStat`
  is to control expose the per stream stat exposed by the core library. It is enabled by default.
- *server_graceful_shutdown_period_ms*: The graceful shutdown period in milliseconds. The default value is 0.
- *server_service_timeout_ms*: The timeout period for the execution of a stream operation in write proxy. If it is positive,
  write proxy will timeout requests if they are taking longer time than the threshold. Otherwise, the timeout feature is disabled.
  By default, it is 0 (disabled).
- *server_stream_probation_timeout_ms*: The time period that a stream should be kept in cache in probationary state after service
  timeout, in order to prevent ownership reacquiring. The unit is milliseconds. The default value is 5 minutes.
- *stream_partition_converter_class*: The stream-to-partition convert class. The converter is used to group streams together, which
  these streams can apply same `per-stream` configuration settings or same other constraints. By default, it is an
  `IdentityStreamPartitionConverter` which doesn't group any streams.

Rate Limit Settings
~~~~~~~~~~~~~~~~~~~

This section describes the rate limit settings per write proxy.

All the rate limit settings have both `soft` and `hard` thresholds. If the throughput goes above `soft` limit,
the requests won't be rejected but just logging in the stat. But if the throughput goes above `hard` limit,
the requests would be rejected immediately.

NOTE: `bps` stands for `bytes per second`, while `rps` stands for `requests per second`.

- *bpsSoftServiceLimit*: The soft limit for bps. Setting it to 0 or negative value will disable this feature.
  By default it is disabled.
- *bpsHardServiceLimit*: The hard limit for bps. Setting it to 0 or negative value will disable this feature.
  By default it is disabled.
- *rpsSoftServiceLimit*: The soft limit for rps. Setting it to 0 or negative value will disable this feature.
  By default it is disabled.
- *rpsHardServiceLimit*: The hard limit for rps. Setting it to 0 or negative value will disable this feature.
  By default it is disabled.

There are two additional rate limiting settings that related to stream acquisitions.

- *rpsStreamAcquireServiceLimit*: The rate limit for rps. When the rps goes above this threshold, the write proxy
  will stop accepting serving new streams.
- *bpsStreamAcquireServiceLimit*: The rate limit for bps. When the bps goes above this threshold, the write proxy
  will stop accepting serving new streams.

Stream Limit Settings
~~~~~~~~~~~~~~~~~~~~~

This section describes the stream limit settings per write proxy. They are the constraints that each write proxy
will apply when deciding whether to own given streams.

- *maxAcquiredPartitionsPerProxy*: The maximum number of partitions per stream that a write proxy is allowed to
  serve. Setting it to 0 or negative value will disable this feature. By default it is unlimited.
- *maxCachedPartitionsPerProxy*: The maximum number of partitions per stream that a write proxy is allowed to cache.
  Setting it to 0 or negative value will disable this feature. By default it is unlimited.

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
