As per https://groups.google.com/forum/#!topic/derbyjs/fwz8zdvAShQ, in order for Redis & Derby 0.5 to play well together, you need to add some configurations:

 * Add to /etc/redis/6379.conf:
   appendonly yes
   appendfsync always
 * Add to /etc/sysctl.conf
   vm.overcommit_memory=1
 * Restart server
 * $redis-cli > FLUSHALL
 * mongo myDatabase > db.dropDatabase()