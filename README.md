# docker-graylog-grafana-loki-stack-4-sap-netweaver
## start

```
docker-compose -f docker-compose-graylog.yml up
docker-compose -f docker-compose-grafana-loki.yml up
```
# configuration in hosts file

```
127.0.0.1 graylog
```

## utils

### graylog 

```
curl -v -X POST -H 'Content-Type: application/json' -d '{ "version": "1.1", "host": "example.org", "short_message": "A short message", "level": 5, "_some_info": "foo" }' 'http://graylog:12201/gelf'
```

## based on

https://github.com/grafana/loki/tree/master/production

https://hometechhacker.com/how-to-create-a-graylog-container-in-docker/

https://mfyz.com/quick-and-dirty-set-up-graylog-in-5-minutes-with-docker/
