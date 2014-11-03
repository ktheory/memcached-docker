Memcached 1.4.14 Docker image
=============================

Description
-----------

This is a Memcached 1.4.14 docker images based on Ubuntu 14.10. It is small and basic.

Its features is to delivered memcached service.  
You will be able to choose the memcache size, by default 64Mo, the max connection number, by default 1024 and the bind address ip, by default 0.0.0.0.  
Its display WARNING and ERROR verbose on stdout. Useful for external monitoring.

So, this image respects pragmatic simple vision of Docker.  
If you are looking for a complete VM, just use LXC.  
**LXC** is an amazing product to get fast **full VM** where **Docker** is amazing to get only **one service by VM**.


Usage
-----

Simple use of memcached docker image:

        $ docker run -d -P --name memcached sylvainlasnier/memcached 
	7b71841bc1ff83eaf5ba84c60114c4e1433ad40a235ba4f489d18200f7394795
	$ docker ps
	CONTAINER ID        IMAGE                             COMMAND                CREATED             STATUS              PORTS                      NAMES
	7b71841bc1ff        sylvainlasnier/memcached:latest   "/usr/bin/memcached    6 seconds ago       Up 5 seconds        0.0.0.0:49156->11211/tcp   memcached           

Test it:

	$ nc `docker inspect -f '{{.NetworkSettings.IPAddress}}' 7b7184` 11211
	stats
	STAT uptime 2627
	STAT time 1405695366
	STAT version 1.4.14 (Ubuntu)
	STAT libevent 2.0.21-stable
	...
	STAT reclaimed 0
	END

Please replace container ID in nc command line with your ;)


I use these docker images in production and I assume update.  
Have fun and try my other [docker images](https://hub.docker.com/u/sylvainlasnier/) ^^

