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
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/latest/user_guide/configuration/perlog.rst" data-proofer-ignore>
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
        .. contents:: Per Stream Configuration

Per Stream Configuration
========================

Application is allowed to override `DistributedLogConfiguration` for individual streams. This is archieved
for supplying an overrided `DistributedLogConfiguration` when opening the distributedlog manager.

::

    DistributedLogNamespace namespace = ...;
    DistributedLogConfiguration perStreamConf = new DistributeLogConfiguration();
    perStreamConf.loadConf(...); // load configuration from a per stream configuration file
    DistributedLogManager dlm = namespace.openLog("test-stream", Optional.of(perStreamConf), Optional.absent());

Dynamic Configuration
---------------------

Besides overriding normal `DistributedLogConfiguration` with per stream configuration, DistributedLog also
provides loading some configuration settings dynamically. The per stream dynamic settings are offered in
`DynamicDistributedLogConfiguration`.

File Based Dynamic Configuration
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The default dynamic configuration implementation is based on properties files and reloading the file periodically.

::

    ConcurrentBaseConfiguration defaultConf = ...; // base config to fall through
    int reloadPeriod = 60; // 60 seconds
    TimeUnit reloadUnit = TimeUnit.SECOND;
    String configPath = "/path/to/per/stream/config/file";
    File configFile = new File(configPath);
    // load the fie into a properties configuration builder
    PropertiesConfigurationBuilder properties =
        new PropertiesConfigurationBuilder(configFile.toURI().toURL());
    // Construct the dynamic configuration
    DynamicDistributedLogConfiguration dynConf = new DynamicDistributedLogConfiguration(defaultConf);
    // add a configuration subscription to periodically reload the config from the file
    ConfigurationSubscription subscription =
        new ConfigurationSubscription(dynConf, properties, executorService, reloadPeriod, reloadUnit);

Stream Config Provider
~~~~~~~~~~~~~~~~~~~~~~

The stream config provider is designed to manage and reload dynamic configs for individual streams.

::

    String perStreamConfigDir = "/path/to/per/stream/config/dir";
    String defaultConfigPath = "/path/to/default/config/file";
    StreamPartitionConverter converter = ...;
    ScheduledExecutorService scheduler = ...;
    int reloadPeriod = 60; // 60 seconds
    TimeUnit reloadUnit = TimeUnit.SECOND;
    StreamConfigProvider provider = new ServiceStreamConfigProvider(
        perStreamConfigDir,
        defaultConfigPath,
        converter,
        scheduler,
        reloadPeriod,
        reloadUnit);

    Optional<DynamicDistributedLogConfiguration> streamConf = provider.getDynamicStreamConfig("test-stream");

- *perStreamConfigDir*: The directory contains configuration files for each stream. the file name is `<stream_name>.conf`.
- *defaultConfigPath*: The default configuration file. If there is no stream configuration file found in `perStreamConfigDir`,
  it would load the configuration from `defaultConfigPath`.
- *StreamPartitionConverter*: A converter that convert the stream names to partitions. DistributedLog doesn't provide built-in
  partitions. It leaves partition strategy to application. Application usually put the partition id in the dl stream name. So the
  converter is for group the streams and apply same configuration. For example, if application uses 3 streams and names them as
  `test-stream_000001`, `test-stream_000002` and `test-stream_000003`, a `StreamPartitionConverter` could be used to categorize them
  as partitions for stream `test-stream` and apply the configuration from file `test-stream.conf`.
- *scheduler*: The executor service that reloads configuration periodically.
- *reloadPeriod*: The reload period, in `reloadUnit`.

Available Dynamic Settings
~~~~~~~~~~~~~~~~~~~~~~~~~~

Storage Settings
~~~~~~~~~~~~~~~~

- *logSegmentRetentionHours*: The log segment retention period, in hours. In other words, how long should DL keep the log segment once it is `truncated` or `completed`.
- *bkcEnsembleSize*: The ensemble size of the log segment. The default value is 3.
- *bkcWriteQuorumSize*: The write quorum size of the log segment. The default value is 3.
- *bkcAckQuorumSize*: The ack quorumm size of the log segment. The default value is 2.

Transmit Settings
~~~~~~~~~~~~~~~~~

- *writerOutputBufferSize*: The output buffer size in bytes. Larger buffer size will result in higher compression ratio and
  it would reduce the entries sent to bookkeeper, use the disk bandwidth more efficiently and improve throughput.
  Set this setting to `0` will ask DL to transmit the data immediately, which it would achieve low latency.

Durability Settings
~~~~~~~~~~~~~~~~~~~

- *isDurableWriteEnabled*: The flag indicates whether durable write is enabled. By default it is true.

ReadAhead Settings
~~~~~~~~~~~~~~~~~~

- *readAheadMaxRecords*: The maximum number of records that will be cached in readahead cache by the DL readers. The default value
  is 10. A higher value will improve throughput but use more memory. It should be tuned properly to avoid jvm gc if the reader cannot
  keep up with the writing rate.
- *readAheadBatchSize*: The maximum number of entries that readahead worker will read in one batch. The default value is 2.
  Increase the value to increase the concurrency of reading entries from bookkeeper. It is recommended to tune to a proper value for
  catching up readers, not to exhaust bookkeeper's bandwidth.

Rate Limit Settings
~~~~~~~~~~~~~~~~~~~

All the rate limit settings have both `soft` and `hard` thresholds. If the throughput goes above `soft` limit,
the requests won't be rejected but just logging in the stat. But if the throughput goes above `hard` limit,
the requests would be rejected immediately.

NOTE: `bps` stands for `bytes per second`, while `rps` stands for `requests per second`.

- *bpsSoftWriteLimit*: The soft limit for bps. Setting it to 0 or negative value will disable this feature.
  By default it is disabled.
- *bpsHardWriteLimit*: The hard limit for bps. Setting it to 0 or negative value will disable this feature.
  By default it is disabled.
- *rpsSoftWriteLimit*: The soft limit for rps. Setting it to 0 or negative value will disable this feature.
  By default it is disabled.
- *rpsHardWriteLimit*: The hard limit for rps. Setting it to 0 or negative value will disable this feature.
  By default it is disabled.

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
