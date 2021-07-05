# PEP VM Individual Setups
All of the following was tested to work on CentOS 7
## VM 6 (3* ZEUS)
- Install Docker: [tutorial](https://docs.docker.com/engine/install/centos/)
- Installation of Zeus x3 in different folders, without the `web` container: [tutorial](https://github.com/knowledge-gr/evoting)
- Change settings files: `local.env`, `docker-compose.yml`, `docker_settings.py`
- Run them on different ports
- Setup NGINX to map domains to docker instances: [tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-centos-7)
- Setup letsencrypt certbot: [tutorial](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-centos-7)
- Drop firewall for HTTP/HTTPS requests
- Tweak NGINX settings (check `/docker/config/nginx.conf` in the default ZEUS install for boilerplate nginx config)

### Ports
- pella: 3000
- pieria: 3001
- lesvos: 3002

### Domains
#### Zeus
- pella: [https://evoting.pellachamber.e-host.gr/](https://evoting.pellachamber.e-host.gr/)
- pieria: [https://evoting.champier.e-host.gr/](https://evoting.champier.e-host.gr/)
- lesvos: [https://evoting.lesvos-chamber.e-host.gr/](https://evoting.lesvos-chamber.e-host.gr/)

### TODO
- Change website title?
- Set admins list (names, emails)
- Question limit?

## VM 7 and 8 (1* WSO2APIM each)
- Install Docker: [tutorial](https://docs.docker.com/engine/install/centos/)
- Clone WSO2 API Manager (for Docker install). My tutorial that mentions docker is [here](https://github.com/knowledge-gr/ws02-nestjsdemo/blob/master/ws02/installation.md). Simply include the config files as volumes in the docker container
- Change settings files, mainly `deployment.toml`
- Run using Docker (include volumes for settings and expose ports 9443, 8280)
- Setup NGINX to map domains to APIM and APIGW: [tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-centos-7)
- Setup letsencrypt certbot: [tutorial](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-centos-7)
- Drop firewall for HTTP/HTTPS requests

### Ports
- APIM: 9443
- APIGW: 8280 (HTTP) and 8243 (HTTPS)

### Domains
- pella: [https://apim.pellachamber.e-host.gr/devportal](https://apim.pellachamber.e-host.gr/devportal)
- pieria: [https://apim.champier.e-host.gr/devportal](https://apim.champier.e-host.gr/devportal)

