# PEP VM Individual Setups
All of the following was tested to work on CentOS 7
## VM 6
- Install Docker: [tutorial](https://docs.docker.com/engine/install/centos/)
- Default Installation of Zeus x3 in different folders: [tutorial](https://github.com/knowledge-gr/evoting)
- Change settings: user/pass, db, cores, host, serverURL
- Run them in 3 different docker containers
- Setup NGINX to map domains to docker instances: [tutorial](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-centos-7)
- Setup letsencrypt certbot: [tutorial](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-centos-7)
- Drop firewall for HTTP/HTTPS requests
- Map URLs

### Ports
#### Zeus
- pella: 8000
- pieria: 8001
- lesvos: 8002

### Domains
#### Zeus
- pella: [https://evoting.pellachamber.e-host.gr/](https://evoting.pellachamber.e-host.gr/)

### TODO
- Find SMTP settings
- Change website title?
- Set admin email
- Question limit?
