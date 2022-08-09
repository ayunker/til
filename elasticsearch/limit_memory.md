# Limit Memory Usage

When Elasticsearch runs, it will consume as much memory as it can. This is great on a server, not so great on localhost.

To limit memory usage, need to edit the `jvm.options` file. This isn't the easiest to find.

On M1 macOS, it's located at:
```
/opt/homebrew/Cellar/elasticsearch-full/7.17.4/libexec/config/jvm.options
```

Edit the below section to spcify JVM heap size -> limit memory it uses.
 
```
################################################################
## IMPORTANT: JVM heap size
################################################################
##
## The heap size is automatically configured by Elasticsearch
## based on the available memory in your system and the roles
## each node is configured to fulfill. If specifying heap is
## required, it should be done through a file in jvm.options.d,
## and the min and max should be set to the same value. For
## example, to set the heap to 4 GB, create a new file in the
## jvm.options.d directory containing these lines:
##
-Xms4g
-Xmx4g
##
## See https://www.elastic.co/guide/en/elasticsearch/reference/7.17/heap-size.html
## for more information
##
################################################################
```
