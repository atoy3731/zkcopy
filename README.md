# zkcopy

Tool for fast copying ZooKeeper data between different clusters.
Originally it was developed for copying big volumes of configuration over WAN.

This will NOT delete old znodes, and WILL copy all ephermal nodes.

## Build

Requires [apache maven 3](https://maven.apache.org/).

```bash
mvn clean install
```

## Usage

```bash
java -jar target/zkcopy.jar --source server:port/path --target server:port/path
```

With [docker](https://hub.docker.com/r/ksprojects/zkcopy/), use following commands:

```bash
docker pull ksprojects/zkcopy
docker run --rm -it ksprojects/zkcopy --source server:port/path --target server:port/path
```

## Options

```
 -h,--help                                print this message
 -s,--source <server:port/path>           location of a source tree to
                                          copy
 -t,--target <server:port/path>           target location
 -w,--workers <N>                         (optional) number of concurrent
                                          workers to copy data
```