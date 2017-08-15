<!DOCTYPE html>
<html lang="en">

  <head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>Download Releases</title>
  <meta name="description" content="Apache DistributedLog is an high performance replicated log.
">

  <link rel="stylesheet" href="/distributedlog-staging-site/styles/site.css">
  <link rel="stylesheet" href="/distributedlog-staging-site/css/theme.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js"></script>
  <script src="/distributedlog-staging-site/js/bootstrap.min.js"></script>
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/0.4.0-incubating/start/download.rst" data-proofer-ignore>
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
        .. contents:: This page covers how to download DistributedLog releases.

Releases
========

`0.4.0-incubating` is the latest release.

You can verify your download by checking its md5 and sha1.

0.4.0-incubating
~~~~~~~~~~~~~~~~

This is the first Apache release. Download here_.

- `Release Notes`_
- `Announce Blog Post`_

.. _here: https://dist.apache.org/repos/dist/release/bookkeeper/distributedlog/0.4.0-incubating
.. _Release Notes: https://issues.apache.org/jira/secure/ReleaseNote.jspa?projectId=12320620&version=12337980
.. _Announce Blog Post: /releases/2017/04/23/the-first-release.html


The releases before Apache Incubating are also listed as below:

0.3.51-RC1
~~~~~~~~~~

This is the second release candidate for 0.3.51.

- Source download: 0.3.51-RC1.zip_
- Binary downloads: 
    - Service: distributedlog-service-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip_
    - Benchmark: distributedlog-benchmark-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip_
    - Tutorials: distributedlog-tutorials-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip_
    - All: distributedlog-all-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip_

.. _0.3.51-RC1.zip: https://github.com/twitter/distributedlog/archive/0.3.51-RC1.zip
.. _distributedlog-all-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip: https://github.com/twitter/distributedlog/releases/download/0.3.51-RC1/distributedlog-all-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip
.. _distributedlog-service-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip: https://github.com/twitter/distributedlog/releases/download/0.3.51-RC1/distributedlog-service-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip
.. _distributedlog-benchmark-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip: https://github.com/twitter/distributedlog/releases/download/0.3.51-RC1/distributedlog-benchmark-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip
.. _distributedlog-tutorials-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip: https://github.com/twitter/distributedlog/releases/download/0.3.51-RC1/distributedlog-tutorials-3ff9e33fa577f50eebb8ee971ddb265c971c3717.zip

0.3.51-RC0
~~~~~~~~~~

This is the first release candidate for 0.3.51_.

- Source download: 0.3.51-RC0.zip_
- Binary downloads: 
    - Service: distributedlog-service-63d214d3a739cb58a71a8b51127f165d15f00584.zip_
    - Benchmark: distributedlog-benchmark-63d214d3a739cb58a71a8b51127f165d15f00584.zip_
    - Tutorials: distributedlog-tutorials-63d214d3a739cb58a71a8b51127f165d15f00584.zip_
    - All: distributedlog-all-63d214d3a739cb58a71a8b51127f165d15f00584.zip_

.. _0.3.51: https://github.com/twitter/distributedlog/releases/tag/0.3.51-RC0
.. _0.3.51-RC0.zip: https://github.com/twitter/distributedlog/archive/0.3.51-RC0.zip
.. _distributedlog-all-63d214d3a739cb58a71a8b51127f165d15f00584.zip: https://github.com/twitter/distributedlog/releases/download/0.3.51-RC0/distributedlog-all-63d214d3a739cb58a71a8b51127f165d15f00584.zip
.. _distributedlog-service-63d214d3a739cb58a71a8b51127f165d15f00584.zip: https://github.com/twitter/distributedlog/releases/download/0.3.51-RC0/distributedlog-service-63d214d3a739cb58a71a8b51127f165d15f00584.zip
.. _distributedlog-benchmark-63d214d3a739cb58a71a8b51127f165d15f00584.zip: https://github.com/twitter/distributedlog/releases/download/0.3.51-RC0/distributedlog-benchmark-63d214d3a739cb58a71a8b51127f165d15f00584.zip
.. _distributedlog-tutorials-63d214d3a739cb58a71a8b51127f165d15f00584.zip: https://github.com/twitter/distributedlog/releases/download/0.3.51-RC0/distributedlog-tutorials-63d214d3a739cb58a71a8b51127f165d15f00584.zip

Maven Dependencies
==================

You can add the following dependencies to your `pom.xml` to include Apache DistributedLog in your project.

.. code-block:: xml

  <!-- use core library to access DL storage -->
  <dependency>
    <groupId>com.twitter</groupId>
    <artifactId>distributedlog-core_2.11</artifactId>
    <version>0.3.51-RC1</version>
  </dependency>
  <!-- use thin proxy client to access DL via write proxy -->
  <dependency>
    <groupId>com.twitter</groupId>
    <artifactId>distributedlog-client_2.11</artifactId>
    <version>0.3.51-RC1</version>
  </dependency>

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
