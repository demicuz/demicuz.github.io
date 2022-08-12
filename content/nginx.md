---
title: "nginx"
---

### Notes
All configuration files are located in the `/etc/nginx` directory.

By default, nginx serves a static website from `/var/www/html`.
Send signals with `nginx -s <signal>`
- `stop` - fast shutdown
- `quit` - graceful shutdown
- `reload` - reloading the configuration file

### Docs
- [Getting Started | NGINX](https://www.nginx.com/resources/wiki/start/)
- [Pitfalls and Common Mistakes | NGINX](https://www.nginx.com/resources/wiki/start/topics/tutorials/config_pitfalls/)

### See also
- [[uWSGI]] the server and `uwsgi` the protocol

### Links
- [How to Install Nginx](https://linuxize.com/post/how-to-install-nginx-on-ubuntu-20-04/) - has some useful info on how to get started
- [How do I know if nginx is running Ubuntu?](https://frameboxxindore.com/linux/how-do-i-know-if-nginx-is-running-ubuntu.html) - and how to change default port
- [Nginx 403 forbidden for all files](https://stackoverflow.com/questions/6795350)
