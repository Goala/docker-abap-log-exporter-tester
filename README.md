# docker-graylog-grafana-loki-stack-4-sap-netweaver
## start

```
docker-compose -f docker-compose-graylog.yml up
docker-compose -f docker-compose-grafana-loki.yml up
```
## configuration in hosts file

```
127.0.0.1 graylog
```

## utils

### Loki

```
curl -v -H "Content-Type: application/json" -XPOST -s "http://localhost:3100/api/prom/push" --data-raw '{"streams": [{ "labels": "{foo=\"bar\"}", "entries": [{ "ts": "2020-04-11T14:01:06.801064-04:00", "line": "fizzbuzz" }] }]}'
```

### graylog 

```
curl -v -X POST -H 'Content-Type: application/json' -d '{ "version": "1.1", "host": "example.org", "short_message": "A short message", "level": 5, "_some_info": "foo" }' 'http://graylog:12201/gelf'
```

## based on

### Loki

https://github.com/grafana/loki/tree/master/production

### graylog

https://hometechhacker.com/how-to-create-a-graylog-container-in-docker/

https://mfyz.com/quick-and-dirty-set-up-graylog-in-5-minutes-with-docker/
