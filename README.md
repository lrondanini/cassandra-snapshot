# cassandra-snapshot

Scripts to manage snapshots in Cassandra

The scope of this project is to make it easier to backup a cassandra cluster combine snapshots and incremental backups.

## getSnapshot

First, you need to configure the script. Just open getSnapshot and edit the following:

```
#Cassandra Home:

IP="10.138.0.23"
CHOME="./apache-cassandra-3.11.3"

#where to store the new snapshot
BASEDIR="./cassandra_snapshot"

#where to move previous snapshots (if any)
PREVSNAPSHOTSDIR="./previous_snapshot"

#cql version
C_VERSION="3"
```

To snapshot a single keyspace

```
./getSnapshot -k keyspace_name
```

To skip a keyspace(s):

```
./getSnapshot -s keyspace_name1,keyspace_name2,...
```

## loadSnapshot

You also need to configure this script, but just cassandra's information:

```
#Cassandra Home:

IP="10.138.0.23"
CHOME="./apache-cassandra-3.11.3"
```

To specify snapshot folder:

```
./loadSnapshot -f ./snapshot-2019-06-05
```

To load a specify keyspace:

```
./loadSnapshot -f ./snapshot-2019-06-05 -k keyspace_name
```

To skip a keyspace(s):

```
./loadSnapshot -f ./snapshot-2019-06-05 -s keyspace_name1,keyspace_name2
```

To skip schema creation:

```
./loadSnapshot -f ./snapshot-2019-06-05 -c
```
