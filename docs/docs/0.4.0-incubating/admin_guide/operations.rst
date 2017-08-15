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
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/0.4.0-incubating/admin_guide/operations.rst" data-proofer-ignore>
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
        .. contents:: DistributedLog Operations

DistributedLog Operations
=========================

Feature Provider
~~~~~~~~~~~~~~~~

DistributedLog uses a `feature-provider` library provided by Apache BookKeeper for managing features
dynamically at runtime. It is a feature-flag_ system used to proportionally control what features
are enabled for the system. In other words, it is a way of altering the control in a system without
restarting it. It can be used during all stages of development, its most visible use case is on
production. For instance, during a production release, you can enable or disable individual features,
control the data flow through the system, thereby minimizing risk of system failure in real time.

.. _feature-flag: https://en.wikipedia.org/wiki/Feature_toggle

This `feature-provider` interface is pluggable and easy to integrate with any configuration management
system.

API
___

`FeatureProvider` is a provider that manages features under different scopes. The provider is responsible
for loading features dynamically at runtime. A `Feature` is a numeric flag that control how much percentage
of this feature will be available to the system - the number is called `availability`.

::

    Feature.name() => returns the name of this feature
    Feature.availability() => returns the availability of this feature
    Feature.isAvailable() => returns true if its availability is larger than 0; otherwise false


It is easy to obtain a feature from the provider by just providing a feature name.

::

    FeatureProvider provider = ...;
    Feature feature = provider.getFeature("feature1"); // returns the feature named 'feature1'

    
The `FeatureProvider` is scopable to allow creating features in a hierarchical way. For example, if a system
is comprised of two subsystems, one is *cache*, while the other one is *storage*. so the features belong to
different subsystems can be created under different scopes.

::

    FeatureProvider provider = ...;
    FeatureProvider cacheFeatureProvider = provider.scope("cache");
    FeatureProvider storageFeatureProvider = provider.scope("storage");
    Feature writeThroughFeature = cacheFeatureProvider.getFeature("write_through");
    Feature duralWriteFeature = storageFeatureProvider.getFeature("dural_write");

    // so the available features under `provider` are: (assume scopes are separated by '.')
    // - 'cache.write_through'
    // - 'storage.dural_write'


The feature provider could be passed to `DistributedLogNamespaceBuilder` when building the namespace,
thereby it would be used for controlling the features exposed under `DistributedLogNamespace`.

::

    FeatureProvider rootProvider = ...;
    FeatureProvider dlFeatureProvider = rootProvider.scope("dlog");
    DistributedLogNamespace namespace = DistributedLogNamespaceBuilder.newBuilder()
        .uri(uri)
        .conf(conf)
        .featureProvider(dlFeatureProvider)
        .build();


The feature provider is loaded by reflection on distributedlog write proxy server. You could specify
the feature provider class name as below. Otherwise it would use `DefaultFeatureProvider`, which disables
all the features by default.

::

    featureProviderClass=org.apache.distributedlog.feature.DynamicConfigurationFeatureProvider



Configuration Based Feature Provider
____________________________________

Beside `DefaultFeatureProvider`, distributedlog also provides a file-based feature provider - it loads
the features from properties files.

All the features and their availabilities are configured in properties file format. For example,

::

    cache.write_through=100
    storage.dural_write=0


You could configure `featureProviderClass` in distributedlog configuration file by setting it to
`org.apache.distributedlog.feature.DynamicConfigurationFeatureProvider` to enable file-based feature
provider. The feature provider will load the features from two files, one is base config file configured
by `fileFeatureProviderBaseConfigPath`, while the other one is overlay config file configured by
`fileFeatureProviderOverlayConfigPath`. Current implementation doesn't differentiate these two files
too much other than the `overlay` config will override the settings in `base` config. It is recommended
to have a base config file for storing the default availability values for your system and dynamically
adjust the availability values in overlay config file.

::

    featureProviderClass=org.apache.distributedlog.feature.DynamicConfigurationFeatureProvider
    fileFeatureProviderBaseConfigPath=/path/to/base/config
    fileFeatureProviderOverlayConfigPath=/path/to/overlay/config
    // how frequent we reload the config files
    dynamicConfigReloadIntervalSec=60


Available Features
__________________

Check the Features_ reference page for the features exposed by DistributedLog.

.. _Features: ../user_guide/references/features

`dlog`
~~~~~~

A CLI is provided for inspecting DistributedLog streams and metadata.

.. code:: bash

   dlog
   JMX enabled by default
   Usage: dlog <command>
   where command is one of:
       local               Run distributedlog sandbox
       example             Run distributedlog example
       tool                Run distributedlog tool
       proxy_tool          Run distributedlog proxy tool to interact with proxies
       balancer            Run distributedlog balancer
       admin               Run distributedlog admin tool
       help                This help message

   or command is the full name of a class with a defined main() method.

   Environment variables:
       DLOG_LOG_CONF        Log4j configuration file (default $HOME/src/distributedlog/distributedlog-service/conf/log4j.properties)
       DLOG_EXTRA_OPTS      Extra options to be passed to the jvm
       DLOG_EXTRA_CLASSPATH Add extra paths to the dlog classpath

These variable can also be set in conf/dlogenv.sh

Create a stream
_______________

To create a stream:

.. code:: bash

   dlog tool create -u <DL URI> -r <STREAM PREFIX> -e <STREAM EXPRESSION>


List the streams
________________

To list all the streams under a given DistributedLog namespace:

.. code:: bash

   dlog tool list -u <DL URI>

Show stream's information
_________________________

To view the metadata associated with a stream:

.. code:: bash

   dlog tool show -u <DL URI> -s <STREAM NAME>


Dump a stream
_____________

To dump the items inside a stream:

.. code:: bash

   dlog tool dump -u <DL URI> -s <STREAM NAME> -o <START TXN ID> -l <NUM RECORDS>

Delete a stream
_______________

To delete a stream, run:

.. code:: bash

   dlog tool delete -u <DL URI> -s <STREAM NAME>


Truncate a stream
_________________

Truncate the streams under a given DistributedLog namespace. You could specify a filter to match the streams that you want to truncate.

There is a difference between the ``truncate`` and ``delete`` command. When you issue a ``truncate``, the data will be purge without removing the streams. A ``delete`` will delete the stream. You can pass the flag ``-delete`` to the ``truncate`` command to also delete the streams.

.. code:: bash

   dlog tool truncate -u <DL URI>

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
