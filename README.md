## About

This is a fork of the https://github.com/bradfitz/gomemcache

## 🤷‍Why ami I doing this?
In the original repo, the MaxIdleConns only limit idle connections but not the concurrent connections to memcached. So you would have a large number of one-time connections in a moment when high concurrency. As is known to all, memcached connections couldn't close gracefully. There may be a large number of **CLOSE_WAIT** connections in your system.


## What's new
* Limit maximum number of concurrent connections to memcached.
* Use go channel for connection pool.
* Keep each connection in pool alive.


