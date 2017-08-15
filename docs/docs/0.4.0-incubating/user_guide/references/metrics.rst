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
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/0.4.0-incubating/user_guide/references/metrics.rst" data-proofer-ignore>
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
        .. contents:: Metrics

Metrics
=======

This section lists the metrics exposed by main classes.

({scope} is referencing current scope value of passed in StatsLogger.)

MonitoredFuturePool
-------------------

**{scope}/tasks_pending**

Gauge. How many tasks are pending in this future pool? If this value becomes high, it means that
the future pool execution rate couldn't keep up with submission rate. That would be cause high
*task_pending_time* hence affecting the callers that use this future pool.
It could also cause heavy jvm gc if this pool keeps building up.

**{scope}/task_pending_time**

OpStats. It measures the characteristics about the time that tasks spent on waiting being executed.
It becomes high because either *tasks_pending* is building up or *task_execution_time* is high blocking other
tasks to execute.

**{scope}/task_execution_time**

OpStats. It measures the characteristics about the time that tasks spent on execution. If it becomes high,
it would block other tasks to execute if there isn't enough threads in this executor, hence cause high
*task_pending_time* and impact user end latency.

**{scope}/task_enqueue_time**

OpStats. The time that tasks spent on submission. The submission time would also impact user end latency.

MonitoredScheduledThreadPoolExecutor
------------------------------------

**{scope}/pending_tasks**

Gauge. How many tasks are pending in this thread pool executor? If this value becomes high, it means that
the thread pool executor execution rate couldn't keep up with submission rate. That would be cause high
*task_pending_time* hence affecting the callers that use this executor. It could also cause heavy jvm gc if
queue keeps building up.

**{scope}/completed_tasks**

Gauge. How many tasks are completed in this thread pool executor?

**{scope}/total_tasks**

Gauge. How many tasks are submitted to this thread pool executor?

**{scope}/task_pending_time**

OpStats. It measures the characteristics about the time that tasks spent on waiting being executed.
It becomes high because either *pending_tasks* is building up or *task_execution_time* is high blocking other
tasks to execute.

**{scope}/task_execution_time**

OpStats. It measures the characteristics about the time that tasks spent on execution. If it becomes high,
it would block other tasks to execute if there isn't enough threads in this executor, hence cause high
*task_pending_time* and impact user end latency.

OrderedScheduler
----------------

OrderedScheduler is a thread pool based *ScheduledExecutorService*. It is comprised with multiple
MonitoredScheduledThreadPoolExecutor_. Each MonitoredScheduledThreadPoolExecutor_ is wrapped into a
MonitoredFuturePool_. So there are aggregated stats and per-executor stats exposed.

Aggregated Stats
~~~~~~~~~~~~~~~~

**{scope}/task_pending_time**

OpStats. It measures the characteristics about the time that tasks spent on waiting being executed.
It becomes high because either *pending_tasks* is building up or *task_execution_time* is high blocking other
tasks to execute.

**{scope}/task_execution_time**

OpStats. It measures the characteristics about the time that tasks spent on execution. If it becomes high,
it would block other tasks to execute if there isn't enough threads in this executor, hence cause high
*task_pending_time* and impact user end latency.

**{scope}/futurepool/tasks_pending**

Gauge. How many tasks are pending in this future pool? If this value becomes high, it means that
the future pool execution rate couldn't keep up with submission rate. That would be cause high
*task_pending_time* hence affecting the callers that use this future pool.
It could also cause heavy jvm gc if this pool keeps building up.

**{scope}/futurepool/task_pending_time**

OpStats. It measures the characteristics about the time that tasks spent on waiting being executed.
It becomes high because either *tasks_pending* is building up or *task_execution_time* is high blocking other
tasks to execute.

**{scope}/futurepool/task_execution_time**

OpStats. It measures the characteristics about the time that tasks spent on execution. If it becomes high,
it would block other tasks to execute if there isn't enough threads in this executor, hence cause high
*task_pending_time* and impact user end latency.

**{scope}/futurepool/task_enqueue_time**

OpStats. The time that tasks spent on submission. The submission time would also impact user end latency.

Per Executor Stats
~~~~~~~~~~~~~~~~~~

Stats about individual executors are exposed under *{scope}/{name}-executor-{id}-0*. *{name}* is the scheduler
name and *{id}* is the index of the executor in the pool. The corresponding stats of its futurepool are exposed
under *{scope}/{name}-executor-{id}-0/futurepool*. See MonitoredScheduledThreadPoolExecutor_ and MonitoredFuturePool_
for more details.

ZooKeeperClient
---------------

Operation Stats
~~~~~~~~~~~~~~~

All operation stats are exposed under {scope}/zk. The stats are **latency** *OpStats*
on zookeeper operations.

**{scope}/zk/{op}**

latency stats on operations.
these operations are *create_client*, *get_data*, *set_data*, *delete*, *get_children*, *multi*, *get_acl*, *set_acl* and *sync*.

Watched Event Stats
~~~~~~~~~~~~~~~~~~~

All stats on zookeeper watched events are exposed under {scope}/watcher. The stats are *Counter* about the watched events that this client received:

**{scope}/watcher/state/{keeper_state}**

the number of `KeeperState` changes that this client received. The states are *Disconnected*, *SyncConnected*,
*AuthFailed*, *ConnectedReadOnly*, *SaslAuthenticated* and *Expired*. By monitoring metrics like *SyncConnected*
or *Expired* it would help understanding the healthy of this zookeeper client.

**{scope}/watcher/events/{event}**

the number of `Watcher.Event` received by this client. Those events are *None*, *NodeCreated*, *NodeDeleted*,
*NodeDataChanged*, *NodeChildrenChanged*.

Watcher Manager Stats
~~~~~~~~~~~~~~~~~~~~~

This ZooKeeperClient provides a watcher manager to manage watchers for applications. It tracks the mapping between
paths and watcher. It is the way to provide the ability on removing watchers. The stats are *Gauge* about the number
of watchers managed by this zookeeper client.

**{scope}/watcher_manager/total_watches**

total number of watches that are managed by this watcher manager. If it keeps growing, it usually means that
watchers are leaking (resources aren't closed properly). It will cause OOM.

**{scope}/watcher_manager/num_child_watches**

total number of paths that are watched by this watcher manager.

BookKeeperClient
----------------

TODO: add bookkeeper stats there

DistributedReentrantLock
------------------------

All stats related to locks are exposed under {scope}/lock.

**{scope}/acquire**

OpStats. It measures the characteristics about the time that spent on acquiring locks.

**{scope}/release**

OpStats. It measures the characteristics about the time that spent on releasing locks.

**{scope}/reacquire**

OpStats. The lock will be expired when the underneath zookeeper session expired. The
reentrant lock will attempt to re-acquire the lock automatically when session expired.
This metric measures the characteristics about the time that spent on re-acquiring locks.

**{scope}/internalTryRetries**

Counter. The number of retries that locks spend on re-creating internal locks. Typically,
a new internal lock will be created when session expired.

**{scope}/acquireTimeouts**

Counter. The number of timeouts that caller experienced when acquiring locks.

**{scope}/tryAcquire**

OpStats. It measures the characteristics about the time that each internal lock spent on
acquiring.

**{scope}/tryTimeouts**

Counter. The number of timeouts that internal locks try acquiring.

**{scope}/unlock**

OpStats. It measures the characteristics about the time that the caller spent on unlocking
internal locks.

BKLogHandler
------------

The log handler is a base class on managing log segments. so all the metrics in this class are
related log segments retrieval and exposed under {scope}/logsegments. They are all `OpStats` in
the format of `{scope}/logsegments/{op}`. Those operations are:

* force_get_list: force to get the list of log segments.
* get_list: get the list of the log segments. it might just retrieve from local log segment cache.
* get_filtered_list: get the filtered list of log segments.
* get_full_list: get the full list of log segments.
* get_inprogress_segment: time between the inprogress log segment created and the handler read it.
* get_completed_segment: time between a log segment is turned to completed and the handler read it.
* negative_get_inprogress_segment: record the negative values for `get_inprogress_segment`.
* negative_get_completed_segment: record the negative values for `get_completed_segment`.
* recover_last_entry: recovering last entry from a log segment.
* recover_scanned_entries: the number of entries that are scanned during recovering.

See BKLogWriteHandler_ for write handlers.

See BKLogReadHandler_ for read handlers.

BKLogReadHandler
----------------

The core logic in log reader handle is readahead worker. Most of readahead stats are exposed under
{scope}/readahead_worker.

**{scope}/readahead_worker/wait**

Counter. Number of waits that readahead worker is waiting. If this keeps increasing, it usually means
readahead keep getting full because of reader slows down reading.

**{scope}/readahead_worker/repositions**

Counter. Number of repositions that readhead worker encounters. Reposition means that a readahead worker
finds that it isn't advancing to a new log segment and force re-positioning.

**{scope}/readahead_worker/entry_piggy_back_hits**

Counter. It increases when the last add confirmed being advanced because of the piggy-back lac.

**{scope}/readahead_worker/entry_piggy_back_misses**

Counter. It increases when the last add confirmed isn't advanced by a read entry because it doesn't
iggy back a newer lac.

**{scope}/readahead_worker/read_entries**

OpStats. Stats on number of entries read per readahead read batch.

**{scope}/readahead_worker/read_lac_counter**

Counter. Stats on the number of readLastConfirmed operations

**{scope}/readahead_worker/read_lac_and_entry_counter**

Counter. Stats on the number of readLastConfirmedAndEntry operations.

**{scope}/readahead_worker/cache_full**

Counter. It increases each time readahead worker finds cache become full. If it keeps increasing,
that means reader slows down reading.

**{scope}/readahead_worker/resume**

OpStats. Stats on readahead worker resuming reading from wait state.

**{scope}/readahead_worker/long_poll_interruption**

OpStats. Stats on the number of interruptions happened to long poll. the interruptions are usually
because of receiving zookeeper notifications.

**{scope}/readahead_worker/notification_execution**

OpStats. Stats on executions over the notifications received from zookeeper.

**{scope}/readahead_worker/metadata_reinitialization**

OpStats. Stats on metadata reinitialization after receiving notifcation from log segments updates.

**{scope}/readahead_worker/idle_reader_warn**

Counter. It increases each time the readahead worker detects itself becoming idle.

BKLogWriteHandler
-----------------

Log write handlers are responsible for log segment creation/deletions. All the metrics are exposed under
{scope}/segments.

**{scope}/segments/open**

OpStats. Latency characteristics on starting a new log segment.

**{scope}/segments/close**

OpStats. Latency characteristics on completing an inprogress log segment.

**{scope}/segments/recover**

OpStats. Latency characteristics on recovering a log segment.

**{scope}/segments/delete**

OpStats. Latency characteristics on deleting a log segment.

BKAsyncLogWriter
----------------

**{scope}/log_writer/write**

OpStats. latency characteristics about the time that write operations spent.

**{scope}/log_writer/write/queued**

OpStats. latency characteristics about the time that write operations spent in the queue.
`{scope}/log_writer/write` latency is high might because the write operations are pending
in the queue for long time due to log segment rolling.

**{scope}/log_writer/bulk_write**

OpStats. latency characteristics about the time that bulk_write operations spent.

**{scope}/log_writer/bulk_write/queued**

OpStats. latency characteristics about the time that bulk_write operations spent in the queue.
`{scope}/log_writer/bulk_write` latency is high might because the write operations are pending
in the queue for long time due to log segment rolling.

**{scope}/log_writer/get_writer**

OpStats. the time spent on getting the writer. it could spike when there is log segment rolling
happened during getting the writer. it is a good stat to look into when the latency is caused by
queuing time.

**{scope}/log_writer/pending_request_dispatch**

Counter. the number of queued operations that are dispatched after log segment is rolled. it is
an metric on measuring how many operations has been queued because of log segment rolling.

BKAsyncLogReader
----------------

**{scope}/async_reader/future_set**

OpStats. Time spent on satisfying futures of read requests. if it is high, it means that the caller
takes time on processing the result of read requests. The side effect is blocking consequent reads.

**{scope}/async_reader/schedule**

OpStats. Time spent on scheduling next reads.

**{scope}/async_reader/background_read**

OpStats. Time spent on background reads.

**{scope}/async_reader/read_next_exec**

OpStats. Time spent on executing `reader#readNext()`

**{scope}/async_reader/time_between_read_next**

OpStats. Time spent on between two consequent `reader#readNext()`. if it is high, it means that
the caller is slowing down on calling `reader#readNext()`.

**{scope}/async_reader/delay_until_promise_satisfied**

OpStats. Total latency for the read requests.

**{scope}/async_reader/idle_reader_error**

Counter. The number idle reader errors.

BKDistributedLogManager
-----------------------

Future Pools
~~~~~~~~~~~~

The stats about future pools that used by writers are exposed under {scope}/writer_future_pool,
while the stats about future pools that used by readers are exposed under {scope}/reader_future_pool.
See MonitoredFuturePool_ for detail stats.

Distributed Locks
~~~~~~~~~~~~~~~~~

The stats about the locks used by writers are exposed under {scope}/lock while those used by readers
are exposed under {scope}/read_lock/lock. See DistributedReentrantLock_ for detail stats.

Log Handlers
~~~~~~~~~~~~

**{scope}/logsegments**

All basic stats of log handlers are exposed under {scope}/logsegments. See BKLogHandler_ for detail stats.

**{scope}/segments**

The stats about write log handlers are exposed under {scope}/segments. See BKLogWriteHandler_ for detail stats.

**{scope}/readhead_worker**

The stats about read log handlers are exposed under {scope}/readahead_worker.
See BKLogReadHandler_ for detail stats.

Writers
~~~~~~~

All writer related metrics are exposed under {scope}/log_writer. See BKAsyncLogWriter_ for detail stats.

Readers
~~~~~~~

All reader related metrics are exposed under {scope}/async_reader. See BKAsyncLogReader_ for detail stats.

BKDistributedLogNamespace
-------------------------

ZooKeeper Clients
~~~~~~~~~~~~~~~~~

There are various of zookeeper clients created per namespace for different purposes. They are:

**{scope}/dlzk_factory_writer_shared**

Stats about the zookeeper client shared by all DL writers.

**{scope}/dlzk_factory_reader_shared**

Stats about the zookeeper client shared by all DL readers.

**{scope}/bkzk_factory_writer_shared**

Stats about the zookeeper client used by bookkeeper client that shared by all DL writers.

**{scope}/bkzk_factory_reader_shared**

Stats about the zookeeper client used by bookkeeper client that shared by all DL readers.

See ZooKeeperClient_ for zookeeper detail stats.

BookKeeper Clients
~~~~~~~~~~~~~~~~~~

All the bookkeeper client related stats are exposed directly to current {scope}. See BookKeeperClient_
for detail stats.

Utils
~~~~~

**{scope}/factory/thread_pool**

Stats about the ordered scheduler used by this namespace. See OrderedScheduler_ for detail stats.

**{scope}/factory/readahead_thread_pool**

Stats about the readahead thread pool executor used by this namespace. See MonitoredScheduledThreadPoolExecutor_
for detail stats.

**{scope}/writeLimiter**

Stats about the global write limiter used by list namespace.

DistributedLogManager
~~~~~~~~~~~~~~~~~~~~~

All the core stats about reader and writer are exposed under current {scope} via BKDistributedLogManager_.



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
