hxpro.phpmyadmin
===============

phpMyAdmin is a free software tool written in PHP, intended to handle the administration of MySQL over the Web

Role Variables
--------------

    pma_server_name: localhost
    pma_ssl_cert: /path/to/ssl/cert.pem
    pma_ssl_cert_key: /path/to/ssl/key.pem
    #pma_nginx_access_log: /var/log/nginx/mysql_access.log
    #pma_nginx_error_log: /var/log/nginx/mysql_error.log
    pma_install_path: /var/www/html/phpmyadmin
    pma_phpfpm_listen: "{{ phpfpm_default_listen }}"
    pma_max_navigation_items: 500
    pma_blowfish_secret: 'YOU MUST FILL IN THIS FOR COOKIE AUTH!'
    pma_cfg_servers: []
    pma_allow_from:
      - 127.0.0.1
    pma_default_theme: 'pmahomme'

Dependencies
------------

 - hxpro.bootstrap

Example Playbook
----------------

    - hosts: servers
      roles:
         - role: hxpro.phpmyadmin
           pma_server_name: mysql.example.com
           pma_install_path: /var/www/html/phpmyadmin
           pma_max_navigation_items: 100
           pma_blowfish_secret: 'dc4Us.f6e!4_86/g_-W\+;( &r5R4e46'
           pma_allow_from:
             - 192.168.0.0/24
           pma_cfg_servers:
             - verbose: My MySQL Server
               host: 127.0.0.1

License
-------

WTFPL

Author Information
------------------

Matěj Koudelka <matej@hxpro.cz>
