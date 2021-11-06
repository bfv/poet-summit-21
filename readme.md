# POET Summit 21 - Docker 101

In this repo 2 Docker compose files to showcase OpenEdge with a Traefik load balancer.

The non-https version be can run like:

```
docker compose up --scale pas=3
```

If you own a domain and are able to setup that domain to point to your laptop (port 80 & 443) you can try the secure version as well:

```
docker compose -f docker-compose-https.yaml up --scale pas=3
``` 

In both cases, make sure that the domain in this line resolves to your laptop:


```
- "traefik.http.routers.pas.rule=Host(`poetsummit.bfv.io`)"
```

(for example, in you hosts file: `127.0.0.1 poetsummit.bfv.io` ). Either way, the domain name is important because that's what traefik uses to direct traffic to PAS.

## paths

A few paths which can be used:
```
poetsummit.bfv.io/web/get
poetsummit.bfv.io/web/get?openedge=true
poetsummit.bfv.io/web/customer
poetsummit.bfv.io/web/customer?id=3000
```

