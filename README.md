# REDIS MEMORY DATABASE

https://redis.io/

## Running Redis

-  redis-server
-  redis-server config/redis.conf
-  redis-cli -h localhost -p 6379

### Data String

-  set test "Hello World"
-  get test
-  exists test -> 1
-  append test "add more hello world" -> get test
-  keys \* -> list all keys
-  key test\* -> list all keys that start with test
-  del test (delete key) -> get test -> (nil)

### Data Range

-  set test "Hello World"
-  get test -> setrange test 6 "Redis" -> get test

### Multiple Data String

-  mset key1 "Hello" key2 "World" key3 "Redis"
-  mget key1 key2 key3

### Expiration

-  expire key 10 (seconds)
-  setex key 10 "Hello" (set key and expiration)
-  ttl key (time to live)

### Increment and Decrement

-  incr key
-  decr key
-  get key
-  incrby key [value]
-  decrby key [value]
-  get key

### Flush

-  flushdb (delete all keys in current database)
-  flushall (delete all keys in all databases)

### Pipeline

-  redis-cli -h host -p port -n database --pipe < input-file
   (redis-cli -h localhost -p 6379 -n 0 --pipe < input-file.txt)

### Transaction

-  multi (start transaction)
-  exec (execute transaction)
-  discard (cancel transaction)

### Config

-  config get \* -> list all configurations
-  config get \*max\* -> list all configurations that contains max
-  config get maxmemory -> get maxmemory configuration
-  config get databases
-  config get bind
-  config get save

### Protected Mode

-  redis-cli -h 192.168.1.101 -p 6379
