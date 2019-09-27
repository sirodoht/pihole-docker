# Pi-hole

From https://github.com/pi-hole/docker-pi-hole

## Docker run command

```sh
docker run -d --name pihole -e TZ=Europe/Athens -e WEBPASSWORD=Password -e DNS1=1.1.1.1 -e DNS2=1.0.0.1 -p 53:53/tcp -p 53:53/udp -p 67:67/tcp -p 80:80/tcp -p 443:443 -v $(pwd)/etc-pihole/:/etc/pihole/ -v $(pwd)/etc-dnsmasq.d:/etc/dnsmasq.d/ --dns=127.0.0.1 --dns=1.1.1.1 --cap-add=NET_ADMIN --restart=unless-stopped pihole/pihole:4.3.2-1
```

## Docker compose command

```sh
docker-compose up
```

## Change web admin password

```sh
docker exec -it pihole pihole -a -p newpassword
```

## License

MIT
