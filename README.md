NGINX
=========

nginx installation, and configuration  
Works with `gara2000.ssl_cert` role, version `v1.0.1`, for deploying an SSL certification  

Requirements
------------

- Runs on ubuntu (tested on ubuntu 24.04)

Role Variables
--------------

- domain: your domain name
- main_server: if set to true, than the http server will be set to "default_server"
- servers: list of nginx configuration files for the servers(by default it includes a static http server)
- dependencies: list of dependency modules (empty by default)
- enabled_modules: list of modules to be enabled (empty by default)

Dependencies
------------

- No dependencies

Example Playbook
----------------

```yaml
- hosts: servers
  become: true
  vars:
    context: "."
    html_file: my_website.html
    servers:
      - http
      - rtmp
    dependencies:
      - libnginx-mod-rtmp
    enabled_modules:
      - ngx_rtmp_module.so
  roles:
      - gara2000.nginx
```

License
-------

MIT
