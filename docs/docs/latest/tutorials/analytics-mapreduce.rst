<!DOCTYPE html>
<html lang="en">

  <head>
  <meta charset="utf-8">
  <meta http-equiv="X-UA-Compatible" content="IE=edge">
  <meta name="viewport" content="width=device-width, initial-scale=1">

  <title>Tutorial - DistributedLog meets MapReduce</title>
  <meta name="description" content="Apache DistributedLog is an high performance replicated log.
">

  <link rel="stylesheet" href="/distributedlog-staging-site/styles/site.css">
  <link rel="stylesheet" href="/distributedlog-staging-site/css/theme.css">
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.0/jquery.min.js"></script>
  <script src="/distributedlog-staging-site/js/bootstrap.min.js"></script>
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/latest/tutorials/analytics-mapreduce.rst" data-proofer-ignore>
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
        .. contents:: Tutorial - DistributedLog meets MapReduce

DistributedLog meets MapReduce
==============================

A distributedlog log stream is consists of log segments. Each log segment is distributed
among multiple bookies node. This nature of data distribution allows distributedlog easily
integrated with any analytics processing systems like *MapReduce* and *Spark*. This tutorial
shows how you could use *MapReduce* to process log streams' data in batch and how *MapReduce*
can leverage the data locality of log segments.

InputFormat
~~~~~~~~~~~

**InputFormat** is one of the fundamental class in Hadoop MapReduce framework, that is used
for accessing data from different sources. The class is responsible for defining two main
things:

- Data Splits
- Record Reader

*Data Split* is a fundamental concept in Hadoop MapReduce framework which defines both
the size of individual Map tasks and its potential execution server. The *Record Reader* is
responsible for actual reading records from the *data split* and submitting them (as key/value
pairs) to the mapper.

Using distributedlog log streams as the sources for a MapReduce job, the *log segments* are
the *data splits*, while the *log segment reader* for a log segment is the *record reader* for
a *data split*.

Log Segment vs Data Split
~~~~~~~~~~~~~~~~~~~~~~~~~

Any split implementation extends the Apache base abstract class - **InputSplit**, defining a
split length and locations. A distributedlog log segment has *record count*, which could be used
to define the length of the split, and its metadata contains the storage nodes that are used to
store its log records, which could be used to define the locations of the split. So we could
create a **LogSegmentSplit** wrapping over a *LogSegment* (LogSegmentMetadata and LedgerMetadata).

::

    public class LogSegmentSplit extends InputSplit {

        private LogSegmentMetadata logSegmentMetadata;
        private LedgerMetadata ledgerMetadata;

        public LogSegmentSplit() {}

        public LogSegmentSplit(LogSegmentMetadata logSegmentMetadata,
                               LedgerMetadata ledgerMetadata) {
            this.logSegmentMetadata = logSegmentMetadata;
            this.ledgerMetadata = ledgerMetadata;
        }

    }


The length of the log segment split is the *number of records in the log segment*.

::

    @Override
    public long getLength()
            throws IOException, InterruptedException {
        return logSegmentMetadata.getRecordCount();
    }


The locations of the log segment split are the bookies' addresses in the ensembles of
the log segment.

::

    @Override
    public String[] getLocations()
            throws IOException, InterruptedException {
        Set<String> locations = Sets.newHashSet();
        for (ArrayList<BookieSocketAddress> ensemble : ledgerMetadata.getEnsembles().values()) {
            for (BookieSocketAddress host : ensemble) {
                locations.add(host.getHostName());
            }
        }
        return locations.toArray(new String[locations.size()]);
    }


At this point, we will have a basic **LogSegmentSplit** wrapping *LogSegmentMetadata* and
*LedgerMetadata*. Then we could retrieve the list of log segments of a log stream and construct
corresponding *data splits* in distributedlog inputformat.

::

    public class DistributedLogInputFormat
            extends InputFormat<DLSN, LogRecordWithDLSN> implements Configurable {

        @Override
        public List<InputSplit> getSplits(JobContext jobContext)
                throws IOException, InterruptedException {
            List<LogSegmentMetadata> segments = dlm.getLogSegments();
            List<InputSplit> inputSplits = Lists.newArrayListWithCapacity(segments.size());
            BookKeeper bk = namespace.getReaderBKC().get();
            LedgerManager lm = BookKeeperAccessor.getLedgerManager(bk);
            final AtomicInteger rcHolder = new AtomicInteger(0);
            final AtomicReference<LedgerMetadata> metadataHolder = new AtomicReference<LedgerMetadata>(null);
            for (LogSegmentMetadata segment : segments) {
                final CountDownLatch latch = new CountDownLatch(1);
                lm.readLedgerMetadata(segment.getLedgerId(),
                        new BookkeeperInternalCallbacks.GenericCallback<LedgerMetadata>() {
                    @Override
                    public void operationComplete(int rc, LedgerMetadata ledgerMetadata) {
                        metadataHolder.set(ledgerMetadata);
                        rcHolder.set(rc);
                        latch.countDown();
                    }
                });
                latch.await();
                if (BKException.Code.OK != rcHolder.get()) {
                    throw new IOException("Faild to get log segment metadata for " + segment + " : "
                            + BKException.getMessage(rcHolder.get()));
                }
                inputSplits.add(new LogSegmentSplit(segment, metadataHolder.get()));
            }
            return inputSplits;
        }

    }


Log Segment Record Reader
~~~~~~~~~~~~~~~~~~~~~~~~~

At this point, we know how to break the log streams into *data splits*. Then we need to be able
to create a **RecordReader** for individual *data split*. Since each *data split* is effectively
a *log segment* in distributedlog, it is straight to implement it using distributedlog's log segment
reader. For simplicity, this example uses the raw bk api to access entries, which it doesn't
leverage features like **ReadAhead** provided in distributedlog. It could be changed to
use log segment reader for better performance.

From the *data split*, we know which log segment and its corresponding bookkeeper ledger. Then
we could open the ledger handle when initializing the record reader.

::

    LogSegmentReader(String streamName,
                     DistributedLogConfiguration conf,
                     BookKeeper bk,
                     LogSegmentSplit split)
            throws IOException {
        this.streamName = streamName;
        this.bk = bk;
        this.metadata = split.getMetadata();
        try {
            this.lh = bk.openLedgerNoRecovery(
                    split.getLedgerId(),
                    BookKeeper.DigestType.CRC32,
                    conf.getBKDigestPW().getBytes(UTF_8));
        } catch (BKException e) {
            throw new IOException(e);
        } catch (InterruptedException e) {
            Thread.currentThread().interrupt();
            throw new IOException(e);
        }
    }


Reading records from the *data split* is effectively reading records from the distributedlog
log segment.

::

    try {
        Enumeration<LedgerEntry> entries =
                lh.readEntries(entryId, entryId);
        if (entries.hasMoreElements()) {
            LedgerEntry entry = entries.nextElement();
            Entry.newBuilder()
                    .setLogSegmentInfo(metadata.getLogSegmentSequenceNumber(),
                            metadata.getStartSequenceId())
                    .setEntryId(entry.getEntryId())
                    .setEnvelopeEntry(
                            LogSegmentMetadata.supportsEnvelopedEntries(metadata.getVersion()))
                    .deserializeRecordSet(true)
                    .setInputStream(entry.getEntryInputStream())
                    .buildReader();
        }
        return nextKeyValue();
    } catch (BKException e) {
        throw new IOException(e);
    }


We could calculate the progress by comparing the position with the record count of this log segment.

::

    @Override
    public float getProgress()
            throws IOException, InterruptedException {
        if (metadata.getRecordCount() > 0) {
            return ((float) (readPos + 1)) / metadata.getRecordCount();
        }
        return 1;
    }


Once we have *LogSegmentSplit* and the *LogSegmentReader* over a split. We could hook them up to
implement distributedlog's InputFormat. Please check out the code_ for more details.

.. _code: https://github.com/apache/distributedlog/tree/master/distributedlog-tutorials/distributedlog-mapreduce

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
