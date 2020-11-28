xteve
xteve, in docker with ovpn

docker runs in bridge mode
access xteve webui ip:34400/web/

mounts to use as sample
Container Path: /root/.xteve <> /mnt/user/appdata/xteve/
Container Path: /tmp/xteve <> /tmp/xteve/
while /mnt/user/appdata/ should fit to your system path ...

```
docker run -d \
  --name=xteve \
  --net=host \
  --log-opt max-size=10m \
  --log-opt max-file=3 \
  -e TZ="Europe/Berlin" \
  -v /mnt/user/appdata/xteve/:/root/.xteve:rw \
  -v /mnt/user/appdata/xteve/config/:/config:rw \
  -v /tmp/xteve/:/tmp/xteve:rw \
  tomoli75/xteve_vpn
  ```
