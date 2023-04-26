The base setup to bootstrap your startup.
## Nginx
Bind `app.conf` to `/etc/nginx/conf.d/default.conf`

## Loki
Bind `loki.yml` to `/etc/config/loki.yml`. Bind loki's data folder to `/loki`. You may want to set `user: "0:1000"`

Entrypoint:
```
entrypoint:
  - /usr/bin/loki
  - -config.file=/etc/config/loki.yml
```

## Promtail
Bind `promtail.yml` to `/etc/config/promtail.yml`. Bind promtail's data folder to `/mnt/promtail`. Bind docker logs folder to `/var/lib/docker/containers`

Entrypoint:
```
entrypoint:
  - /usr/bin/promtail
  - -config.file=/etc/config/promtail.yml
```

## Grafana
Bind `datasource.yml` to `/etc/grafana/provisioning/datasources/datasource.yml`. Bind grafana's data folder to `/var/lib/grafana`
