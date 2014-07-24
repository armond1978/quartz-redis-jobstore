quartz-redis-jobstore
=====================

[![Build Status](https://secure.travis-ci.org/jlinn/quartz-redis-jobstore.png?branch=master)](http://travis-ci.org/jlinn/quartz-redis-jobstore)

A [Quartz Scheduler](http://quartz-scheduler.org/) JobStore using [Redis](http://redis.io).

This project was inspired by [redis-quartz](https://github.com/RedisLabs/redis-quartz).

## Requirements
* Java 7 or higher
* Redis 2.6.12 or higher

## Installation
Maven dependency:
```xml
<dependency>
    <groupId>net.joelinn</groupId>
    <artifactId>quartz-redis-jobstore</artifactId>
    <version>0.1.0</version>
</dependency>
```

## Configuration
The following properties may be set in your `quartz.properties` file:
```
# set the scheduler's JobStore class (required)
org.quartz.jobStore.class: net.joelinn.quartz.jobstore.RedisJobStore

# set the Redis host (required)
org.quartz.jobStore.host: <your redis host>

# set the redis port (required)
org.quartz.jobStore.port: <your redis port>

# set the Redis key prefix for all JobStore Redis keys (optional, defaults to none)
org.quartz.jobStore.keyPrefix = a_prefix_

# set the Redis lock timeout in milliseconds (optional, defaults to 30000)
org.quartz.jobStore.lockTimeout = 30000
```

## Limitations
All GroupMatcher comparators have been implemented. 
Aside from that, the same limitations outlined in [redis-quartz's readme](https://github.com/RedisLabs/redis-quartz#limitations) apply.