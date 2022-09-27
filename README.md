# Neo4j is not running?

    ERROR [backup-server] cannot bind to '127.0.0.1:6362' with transport 'EpollServerSocketChannel'. Message: bind(..) failed: Address already in use
or

    Execution of backup failed. null
or

    Caused by: io.netty.channel.unix.Errors$NativeIoException: bind(..) failed: Address already in use
or

    ERROR Failed to start Neo4j on 0.0.0.0:7474.


#### PROBLEM SOLVED

* open the neo4j.log file to see the error

      less neo4j.log

* if the error is the same as this, run this script in logs

      ps -ef | grep 6362
or

      ps -ef | grep neo4j
 
 <img width="928" alt="image" src="https://user-images.githubusercontent.com/110078907/192470178-6da8ea43-91f1-4c6b-9dd7-e68016373c1f.png">
 
* sudo kill -9 2565132 (in this case)

* start Neo4j

      ./neo4j start
 
