# Pihole - Nginx

Serving pihole without exposing port 80

## configuration

**nginx** setup

```
# you may change this part only
    ports:
      - "81:80" # nginx is not supposed to use port 80. Change this to your own port
    environment:
      - LANG=en_EN.UTF-8
      - TZ=UTC
```

**pihole** setup

```
# only change environment variables
    environment:
      ServerIP: 127.0.0.1 # set your own host IP
      TZ: 'UTC'
      WEBPASSWORD: 'YourOwnPassword'
```

## setup

```shell
docker compose up -d
```

enjoy your pihole with reverse proxy