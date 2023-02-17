# ha-network-service-codebase
use Nginx and fastAPI
codebase for ha network service

## Configuration
change `INVENTORY_URL`, `STORAGE_URL` -> [link](https://github.com/YuShuanHsieh/ha-network-service-codebase/blob/main/Deploy/Makefile#L1-L2)

change `upstream server ip` -> [link](https://github.com/YuShuanHsieh/ha-network-service-codebase/blob/main/LoadBalance/nginx.conf#L14)

## deploy business
```
cd deploy
make business
```

## deploy inventory
```
cd deploy
make inventory
```

## deploy storage
```
cd deploy
make storage
```

## deploy proxy
```
cd deploy
make proxy
```


```
curl -X 'POST' 'http://localhost:8100/api/order' -H 'accept: application/json' -H 'Content-Type: application/json' -d '{ "location": "l1", "timestamp": "2023-01-01T20:18:57.424+08:00", "data": {"a": 18,"b": 2,"c": 6, "d": 28} }'
```

```
curl -X 'POST' 'http://localhost:8100/api/order' -H 'accept: application/json' -H 'Content-Type: application/json' -d '{ "location": "l1", "timestamp": "2023-01-01T20:18:58.424+08:00", "data": {"a": 17,"b": 1,"c": 5, "d": 27} }'
```

```
curl -X 'GET' 'http://localhost:8100/api/record?location=l1&date=2023-01-01'
```

```
curl -X 'GET' 'http://localhost:8100/api/report?location=l1&date=2023-01-01'
```
