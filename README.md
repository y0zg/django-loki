# Dockerized Django Logging via Grafana Loki

Current setup uses loki driver

```
git clone https://github.com/y0zg/django-loki.git
cd django-loki/
docker-compose up -d
docker plugin install grafana/loki-docker-driver:latest --alias loki --grant-all-permissions
docker network create blog-net
docker run -d --name loki --restart unless-stopped -p 3100:3100 --network blog-net grafana/loki:latest "-config.file=/etc/loki/local-config.yaml"
```

This repository contains materials for the Medium [post](https://medium.com/@moeenz/48464d13f8cb).
