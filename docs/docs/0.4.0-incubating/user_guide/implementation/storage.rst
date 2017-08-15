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
  <link rel="canonical" href="http://bookkeeper.apache.org/distributedlog/distributedlog-staging-site/docs/0.4.0-incubating/user_guide/implementation/storage.rst" data-proofer-ignore>
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
        .. contents:: Storage

Storage
=======

This describes some implementation details of storage layer.

Ensemble Placement Policy
-------------------------

`EnsemblePlacementPolicy` encapsulates the algorithm that bookkeeper client uses to select a number of bookies from the
cluster as an ensemble for storing data. The algorithm is typically based on the data input as well as the network
topology properties.

By default, BookKeeper offers a `RackawareEnsemblePlacementPolicy` for placing the data across racks within a
datacenter, and a `RegionAwareEnsemblePlacementPolicy` for placing the data across multiple datacenters.

How does EnsemblePlacementPolicy work?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

The interface of `EnsemblePlacementPolicy` is described as below.

::

    public interface EnsemblePlacementPolicy {

        /**
         * Initialize the policy.
         *
         * @param conf client configuration
         * @param optionalDnsResolver dns resolver
         * @param hashedWheelTimer timer
         * @param featureProvider feature provider
         * @param statsLogger stats logger
         * @param alertStatsLogger stats logger for alerts
         */
        public EnsemblePlacementPolicy initialize(ClientConfiguration conf,
                                                  Optional<DNSToSwitchMapping> optionalDnsResolver,
                                                  HashedWheelTimer hashedWheelTimer,
                                                  FeatureProvider featureProvider,
                                                  StatsLogger statsLogger,
                                                  AlertStatsLogger alertStatsLogger);

        /**
         * Uninitialize the policy
         */
        public void uninitalize();

        /**
         * A consistent view of the cluster (what bookies are available as writable, what bookies are available as
         * readonly) is updated when any changes happen in the cluster.
         *
         * @param writableBookies
         *          All the bookies in the cluster available for write/read.
         * @param readOnlyBookies
         *          All the bookies in the cluster available for readonly.
         * @return the dead bookies during this cluster change.
         */
        public Set<BookieSocketAddress> onClusterChanged(Set<BookieSocketAddress> writableBookies,
                                                         Set<BookieSocketAddress> readOnlyBookies);

        /**
         * Choose <i>numBookies</i> bookies for ensemble. If the count is more than the number of available
         * nodes, {@link BKNotEnoughBookiesException} is thrown.
         *
         * @param ensembleSize
         *          Ensemble Size
         * @param writeQuorumSize
         *          Write Quorum Size
         * @param excludeBookies
         *          Bookies that should not be considered as targets.
         * @return list of bookies chosen as targets.
         * @throws BKNotEnoughBookiesException if not enough bookies available.
         */
        public ArrayList<BookieSocketAddress> newEnsemble(int ensembleSize, int writeQuorumSize, int ackQuorumSize,
                                                          Set<BookieSocketAddress> excludeBookies) throws BKNotEnoughBookiesException;

        /**
         * Choose a new bookie to replace <i>bookieToReplace</i>. If no bookie available in the cluster,
         * {@link BKNotEnoughBookiesException} is thrown.
         *
         * @param bookieToReplace
         *          bookie to replace
         * @param excludeBookies
         *          bookies that should not be considered as candidate.
         * @return the bookie chosen as target.
         * @throws BKNotEnoughBookiesException
         */
        public BookieSocketAddress replaceBookie(int ensembleSize, int writeQuorumSize, int ackQuorumSize,
                                                 Collection<BookieSocketAddress> currentEnsemble, BookieSocketAddress bookieToReplace,
                                                 Set<BookieSocketAddress> excludeBookies) throws BKNotEnoughBookiesException;

        /**
         * Reorder the read sequence of a given write quorum <i>writeSet</i>.
         *
         * @param ensemble
         *          Ensemble to read entries.
         * @param writeSet
         *          Write quorum to read entries.
         * @param bookieFailureHistory
         *          Observed failures on the bookies
         * @return read sequence of bookies
         */
        public List<Integer> reorderReadSequence(ArrayList<BookieSocketAddress> ensemble,
                                                 List<Integer> writeSet, Map<BookieSocketAddress, Long> bookieFailureHistory);


        /**
         * Reorder the read last add confirmed sequence of a given write quorum <i>writeSet</i>.
         *
         * @param ensemble
         *          Ensemble to read entries.
         * @param writeSet
         *          Write quorum to read entries.
         * @param bookieFailureHistory
         *          Observed failures on the bookies
         * @return read sequence of bookies
         */
        public List<Integer> reorderReadLACSequence(ArrayList<BookieSocketAddress> ensemble,
                                                List<Integer> writeSet, Map<BookieSocketAddress, Long> bookieFailureHistory);
    }

The methods in this interface covers three parts - 1) initialization and uninitialization; 2) how to choose bookies to
place data; and 3) how to choose bookies to do speculative reads.

Initialization and uninitialization
___________________________________

The ensemble placement policy is constructed by jvm reflection during constructing bookkeeper client. After the
`EnsemblePlacementPolicy` is constructed, bookkeeper client will call `#initialize` to initialize the placement policy.

The `#initialize` method takes a few resources from bookkeeper for instantiating itself. These resources include:

1. `ClientConfiguration` : The client configuration that used for constructing the bookkeeper client. The implementation of the placement policy could obtain its settings from this configuration.
2. `DNSToSwitchMapping`: The DNS resolver for the ensemble policy to build the network topology of the bookies cluster. It is optional.
3. `HashedWheelTimer`: A hashed wheel timer that could be used for timing related work. For example, a stabilize network topology could use it to delay network topology changes to reduce impacts of flapping bookie registrations due to zk session expires.
4. `FeatureProvider`: A feature provider that the policy could use for enabling or disabling its offered features. For example, a region-aware placement policy could offer features to disable placing data to a specific region at runtime.
5. `StatsLogger`: A stats logger for exposing stats.
6. `AlertStatsLogger`: An alert stats logger for exposing critical stats that needs to be alerted.

The ensemble placement policy is a single instance per bookkeeper client. The instance will be `#uninitialize` when
closing the bookkeeper client. The implementation of a placement policy should be responsible for releasing all the
resources that allocated during `#initialize`.

How to choose bookies to place
______________________________

The bookkeeper client discovers list of bookies from zookeeper via `BookieWatcher` - whenever there are bookie changes,
the ensemble placement policy will be notified with new list of bookies via `onClusterChanged(writableBookie, readOnlyBookies)`.
The implementation of the ensemble placement policy will react on those changes to build new network topology. Subsequent
operations like `newEnsemble` or `replaceBookie` hence can operate on the new network topology.

newEnsemble(ensembleSize, writeQuorumSize, ackQuorumSize, excludeBookies)
    Choose `ensembleSize` bookies for ensemble. If the count is more than the number of available nodes,
    `BKNotEnoughBookiesException` is thrown.

replaceBookie(ensembleSize, writeQuorumSize, ackQuorumSize, currentEnsemble, bookieToReplace, excludeBookies)
    Choose a new bookie to replace `bookieToReplace`. If no bookie available in the cluster,
    `BKNotEnoughBookiesException` is thrown.


Both `RackAware` and `RegionAware` placement policies are `TopologyAware` policies. They build a `NetworkTopology` on
responding bookie changes, use it for ensemble placement and ensure rack/region coverage for write quorums - a write
quorum should be covered by at least two racks or regions.

Network Topology
^^^^^^^^^^^^^^^^

The network topology is presenting a cluster of bookies in a tree hierarchical structure. For example, a bookie cluster
may be consists of many data centers (aka regions) filled with racks of machines. In this tree structure, leaves
represent bookies and inner nodes represent switches/routes that manage traffic in/out of regions or racks.

For example, there are 3 bookies in region `A`. They are `bk1`, `bk2` and `bk3`. And their network locations are
`/region-a/rack-1/bk1`, `/region-a/rack-1/bk2` and `/region-a/rack-2/bk3`. So the network topology will look like below:

::

              root
               |
           region-a
             /  \
        rack-1  rack-2
         /  \       \
       bk1  bk2     bk3

Another example, there are 4 bookies spanning in two regions `A` and `B`. They are `bk1`, `bk2`, `bk3` and `bk4`. And
their network locations are `/region-a/rack-1/bk1`, `/region-a/rack-1/bk2`, `/region-b/rack-2/bk3` and `/region-b/rack-2/bk4`.
The network topology will look like below:

::

                    root
                    /  \
             region-a  region-b
                |         |
              rack-1    rack-2
               / \       / \
             bk1  bk2  bk3  bk4

The network location of each bookie is resolved by a `DNSResolver` (interface is described as below). The `DNSResolver`
resolves a list of DNS-names or IP-addresses into a list of network locations. The network location that is returned
must be a network path of the form `/region/rack`, where `/` is the root, and `region` is the region id representing
the data center where `rack` is located. The network topology of the bookie cluster would determine the number of
components in the network path.

::

    /**
     * An interface that must be implemented to allow pluggable
     * DNS-name/IP-address to RackID resolvers.
     *
     */
    @Beta
    public interface DNSToSwitchMapping {
        /**
         * Resolves a list of DNS-names/IP-addresses and returns back a list of
         * switch information (network paths). One-to-one correspondence must be
         * maintained between the elements in the lists.
         * Consider an element in the argument list - x.y.com. The switch information
         * that is returned must be a network path of the form /foo/rack,
         * where / is the root, and 'foo' is the switch where 'rack' is connected.
         * Note the hostname/ip-address is not part of the returned path.
         * The network topology of the cluster would determine the number of
         * components in the network path.
         * <p/>
         *
         * If a name cannot be resolved to a rack, the implementation
         * should return {@link NetworkTopology#DEFAULT_RACK}. This
         * is what the bundled implementations do, though it is not a formal requirement
         *
         * @param names the list of hosts to resolve (can be empty)
         * @return list of resolved network paths.
         * If <i>names</i> is empty, the returned list is also empty
         */
        public List<String> resolve(List<String> names);

        /**
         * Reload all of the cached mappings.
         *
         * If there is a cache, this method will clear it, so that future accesses
         * will get a chance to see the new data.
         */
        public void reloadCachedMappings();
    }

By default, the network topology responds to bookie changes immediately. That means if a bookie's znode appears in  or
disappears from zookeeper, the network topology will add the bookie or remove the bookie immediately. It introduces
instability when bookie's zookeeper registration becomes flapping. In order to address this, there is a `StabilizeNetworkTopology`
which delays removing bookies from network topology if they disappear from zookeeper. It could be enabled by setting
the following option.

::

    # enable stabilize network topology by setting it to a positive value.
    bkc.networkTopologyStabilizePeriodSeconds=10


RackAware and RegionAware
^^^^^^^^^^^^^^^^^^^^^^^^^

`RackAware` placement policy basically just chooses bookies from different racks in the built network topology. It
guarantees that a write quorum will cover at least two racks.

`RegionAware` placement policy is a hierarchical placement policy, which it chooses equal-sized bookies from regions, and
within each region it uses `RackAware` placement policy to choose bookies from racks. For example, if there is 3 regions -
`region-a`, `region-b` and `region-c`, an application want to allocate a 15-bookies ensemble. First, it would figure
out there are 3 regions and it should allocate 5 bookies from each region. Second, for each region, it would use
`RackAware` placement policy to choose 5 bookies.

How to choose bookies to do speculative reads?
______________________________________________

`reorderReadSequence` and `reorderReadLACSequence` are two methods exposed by the placement policy, to help client
determine a better read sequence according to the network topology and the bookie failure history.

In `RackAware` placement policy, the reads will be tried in following sequence:

- bookies are writable and didn't experience failures before
- bookies are writable and experienced failures before
- bookies are readonly
- bookies already disappeared from network topology

In `RegionAware` placement policy, the reads will be tried in similar following sequence as `RackAware` placement policy.
There is a slight different on trying writable bookies: after trying every 2 bookies from local region, it would try
a bookie from remote region. Hence it would achieve low latency even there is network issues within local region.

How to enable different EnsemblePlacementPolicy?
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Users could configure using different ensemble placement policies by setting following options in distributedlog
configuration files.

::

    # enable rack-aware ensemble placement policy
    bkc.ensemblePlacementPolicy=org.apache.bookkeeper.client.RackawareEnsemblePlacementPolicy
    # enable region-aware ensemble placement policy
    bkc.ensemblePlacementPolicy=org.apache.bookkeeper.client.RegionAwareEnsemblePlacementPolicy

The network topology of bookies built by either `RackawareEnsemblePlacementPolicy` or `RegionAwareEnsemblePlacementPolicy`
is done via a `DNSResolver`. The default `DNSResolver` is a script based DNS resolver. It reads the configuration
parameters, executes any defined script, handles errors and resolves domain names to network locations. The script
is configured via following settings in distributedlog configuration.

::

    bkc.networkTopologyScriptFileName=/path/to/dns/resolver/script

Alternatively, the `DNSResolver` could be configured in following settings and loaded via reflection. `DNSResolverForRacks`
is a good example to check out for customizing your dns resolver based our network environments.

::

    bkEnsemblePlacementDnsResolverClass=org.apache.distributedlog.net.DNSResolverForRacks


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
