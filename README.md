# A Dockerized workflow for painless dedicated game server hosting with steamcmd!

![Docker](http://www.docker.com/sites/all/themes/docker/assets/images/logo.png "Docker") ![Steam](http://store.akamai.steamstatic.com/public/shared/images/header/globalheader_logo.png "Steam Powered")

This is a base Ubuntu image with steamcmd installed on top with a top-level mount point (/mnt/steam) ready for Steam dedicated game servers.
Each game server is its own Docker image descended from the parent steamcmd image. Launch using:
```
docker run -dt --name <game> -p <host-port:container-port/udp> -v <host-dir>:/mnt/steam/<game> ianomaly/docker-ubuntu-steamcmd:<game>
```

Examples:
```
docker run -dt --name space-engineers-server -p 8766:8766/udp -p 27016:27016/udp -v /volume1/public/steam/space-engineers-server:/mnt/steam/space-engineers-server ianomaly/docker-ubuntu-steamcmd:space-engineers-server
```

Currently implemented servers:
1. Space Engineers (tag: space-engineers-server)
 
