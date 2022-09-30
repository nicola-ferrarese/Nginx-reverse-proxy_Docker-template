
### Description
This basic project is composed by three services:
* Proxy
  * Service A
  * Service B

**_Only one  is service exposed to the localhost by 8080 port, all services are on different container in the same network_**

The only service exposed is Proxy, accessible at `0.0.0.0:8080`

Once a request is made to the above URL, it is forwarded to Service A, which is accessible also at `0.0.0.0:8080/api_a`

`0.0.0.0:8080/api_b` to be redirected to Service B



### Setup

- create a network for the purpose of the test:
```
docker network create proxy-dev
```
- in the project root:
```
docker-compose build    (opt.) --no-cache
docker-compose up       (opt.) --force-recreate
```