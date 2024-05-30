NGINX
=========

nginx installation, configuration and ssl configuration

Requirements
------------

- Runs on ubuntu 

Role Variables
--------------

- domain: your domain name
- html_file_path: path to static html file
- includes: nginx configuration files (by default it includes a static http server)
- modules: nginx modules to be used 

Dependencies
------------

- No dependencies

Example Playbook
----------------

```yaml
- hosts: servers
  become: yes
  roles:
      - gara2000.nginx
```

License
-------

MIT
