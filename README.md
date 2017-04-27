cassandra-metrics-collector
===========================

This repository hosts a JMX-based metrics collector for cassandra. The
collector sends datapoints to graphite using the same names as cassandra's
graphite dropwizard metrics plugin.

Updating
--------

    $ git clone git@github.com:wikimedia/cassandra-metrics-collector.git
    $ cat <<EOF > ~/.m2/settings.xml
    <settings>
      <servers>
        <server>
          <id>wikimedia.releases</id>
          <username>archiva-deploy</username>
          <password>{secret}</password>
        </server>
        <server>
          <id>wikimedia.snapshots</id>
          <username>archiva-deploy</username>
          <password>{secret}</password>
        </server>
      </servers>
    </settings>
    EOF
    $ mvn deploy
    $ cd /path/to/operations/software/cassandra-metrics-reporter/lib
    $ wget "https://archiva.wikimedia.org/repository/snapshots/org/wikimedia/cassandra-metrics-collector/{version}-SNAPSHOT/cassandra-metrics-collector-{version}-jar-with-dependencies.jar"
    $ git add cassandra-metrics-collector-{version}-jar-with-dependencies.jar
    $ git ci -m 'Commit message'


See also https://phabricator.wikimedia.org/T104208 for additional context.
