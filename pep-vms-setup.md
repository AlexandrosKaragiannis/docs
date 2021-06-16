# PEP VM Individual Setups
All of the following was tested to work on CentOS 7
## VM 6
- Install Docker: [tutorial](https://docs.docker.com/engine/install/centos/)
- Installation of Zeus x3 in different folders, without the `web` container: [tutorial](https://github.com/knowledge-gr/evoting)
- Change settings files: `local.env`, `docker-compose.yml`, `docker_settings.py`
- Run them on different ports
- Setup NGINX to map domains to docker instances: [tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-centos-7)
- Setup letsencrypt certbot: [tutorial](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-centos-7)
- Drop firewall for HTTP/HTTPS requests
- Tweak NGINX settings (check `/docker/config/nginx.conf` in the default ZEUS install for boilerplate nginx config)

### Ports
#### Zeus
- pella: 3000
- pieria: 3001
- lesvos: 3002

### Domains
#### Zeus
- pella: [https://evoting.pellachamber.e-host.gr/zeus/](https://evoting.pellachamber.e-host.gr/zeus/)
- pieria: [https://evoting.champier.e-host.gr/zeus/](https://evoting.champier.e-host.gr/zeus/)
- lesvos: [https://evoting.lesvos-chamber.e-host.gr/zeus/](https://evoting.lesvos-chamber.e-host.gr/zeus/)

### TODO
- Fix I18N
- Change website title?
- Set admins list (names, emails)
- Question limit?
