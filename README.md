# redis-commander
Docker compose for running redis and rediscommander/redis-commander

## alternate method create network

```
docker network create redis-net

docker run -d \
  --name redis \
  --network redis-net \
  -p 6379:6379 \
  redis:7

docker run -d \
  --name redis-commander \
  --network redis-net \
  -p 8081:8081 \
  -e REDIS_HOSTS=local:redis:6379 \
  rediscommander/redis-commander:latest
```
