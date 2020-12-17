# spring-consul-gateway

## Start Consul Agent
```
consul agent -bind=192.168.15.122 -data-dir=~/consul_data -ui -bootstrap-expect=1 -server=1
```

## Start Consul Agent with Docker
```
docker run -d --name consul-1 -p 8500:8500 -e CONSUL_BIND_INTERFACE=eth0 consul
docker run -d --name consul-2 -e CONSUL_BIND_INTERFACE=eth0 -p 8501:8500 consul agent -dev -join=172.17.0.2
docker run -d --name consul-3 -e CONSUL_BIND_INTERFACE=eth0 -p 8502:8500 consul agent -dev -join=172.17.0.2
```

## Start MySQL Server with Docker
```
docker run --name some-mysql -e MYSQL_ROOT_PASSWORD=<password> -e MYSQL_DATABASE=<database> -d mysql:tag --character-set-server=utf8mb4
```
