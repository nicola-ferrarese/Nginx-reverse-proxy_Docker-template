
### Description
This basic project is composed by three services:
* **Proxy** (_https self-signed certificate_)
* **Service A** (Existing project) (_http_)
* **Service B** (Telemetry service) (_http_)

this arrangement allows to connect via SSL to the proxy, while the services will communicate using http.

Since the only access point to the network is through the proxy server the project can be assumed secure.

#### Detail
The project will redirect the connection to `<proxy IP>` and `<proxy IP>/api_a` to **service A**, 

**Service B** can be accessed via `<proxy IP>/api_b`
```
- Service A will be the existing project,
- Service B the telemetry service.
```

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
- Get the ip address of the Proxy container:
```shell
docker inspect -f '{{range.NetworkSettings.Networks}}{{.IPAddress}}{{end}}' proxy_container
```
- Connect via browser:
```
<proxyIP> or
<proxyIP>/api_a or
<proxyIP>/api_b 
```

you will be automatically redirected to the https.