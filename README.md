# jvm-tomcat-config

Create bash script at the same level at the `tomcat` folder
```
#!/bin/sh

export JAVA_HOME=/path/to/java
export JAVA_OPTS='-server -Xms1g -Xmx2g -XX:+AggressiveOpts -XX:CMSInitiatingOccupancyFraction=75 -XX:+UseCMSInitiatingOccupancyOnly -XX:+UseConcMarkSweepGC -XX:+CMSParallelRemarkEnabled -XX:+AlwaysPreTouch -XX:+HeapDumpOnOutOfMemoryError'

/path/to/tomcat/bin/startup.sh
```
Details refer to [here](http://blog.sokolenko.me/2014/11/javavm-options-production.html)

In `conf/server/xml`
```
    <Connector port="8080" protocol="HTTP/1.1"
               maxHttpHeaderSize="8192"
               maxThreads="1024" minSpareThreads="512"
               enableLookups="false"
               connectionTimeout="20000"
               redirectPort="8443" />
```
