# js.graylog2/README.md
This role installs and configure graylog2 single server.   
It has no depencies and is easy to handle.   
Use files in test directory to get started with this role.   


## Execution Requirements
- Tested on CentOS 7

## Role Variables

The following variables can be overridden:
`graylog2_cluster_name`: "graylog"   
`graylog2_root_email`: "graylogadmin@example.com"   
`graylog2_admin_password`: "graylog"   
`graylog2_root_timezone`: "Europe/Zurich"   
`graylog2_allow_highlighting`: true   
`graylog2_dashboard_widget_default_cache_time`: 60s   

`nginx_ssl_cert_dir`: /etc/nginx   
`nginx_ssl_cert_days`: 3650   
`nginx_ssl_cert_host`: "{{ansible_fqdn}}"   
`nginx_ssl_cert_key`: "{{nginx_ssl_cert_host}}_key.pem"   
`nginx_ssl_cert_crt`: "{{nginx_ssl_cert_host}}_crt.pem"   
`nginx_ssl_cert_dhparam`: "{{nginx_ssl_cert_host}}_dhparam.pem"   

`graylog2_transport_email_enabled`: false   
`graylog2_transport_email_hostname`: mail.example.com   
`graylog2_transport_email_port`: 587   
`graylog2_transport_email_use_auth`: true   
`graylog2_transport_email_use_tls`: true   
`graylog2_transport_email_use_ssl`: true   
`graylog2_transport_email_auth_username`: "you@example.com"   
`graylog2_transport_email_auth_password`:  "secret"   
`graylog2_transport_email_subject_prefix`: "[graylog]"   
`graylog2_transport_email_from_email`: "graylog@example.com"   
`graylog2_transport_email_web_interface_url`: "https://{{nginx_ssl_cert_host}}"   

`graylog2_repo_graylog_rpm`: https://packages.graylog2.org/repo/packages/graylog-2.4-repository_latest.rpm   
`graylog2_repo_elasticsearch_url`: https://packages.elastic.co/elasticsearch/2.x/centos   
`graylog2_repo_elasticsearch_key`: https://packages.elastic.co/GPG-KEY-elasticsearch   
`graylog2_repo_mongodb_url`: https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.4/$basearch/   
`graylog2_repo_mongodb_key`: https://www.mongodb.org/static/pgp/server-3.4.asc   

## Features
* Automatic restart of graylog service if config file has changed

## First Graylog Login:
When you first login, define Inputs:
System/Inputs > Inputs > Syslog UDP   
  "launch new input"   
    [x] Global   
    Title: Unix Syslog   
    Port: 1514   
    "Save"   

Now you can send syslog via UDP to Port 1514.   

# example playbooks for this role are located in `test` folder:
* `playbook_graylog2.yml`: Real life example with firewalld configuration


# License
https://opensource.org/licenses/GPL-3.0    
Copyright (c) Chris Ruettimann <chris@bitbull.ch>  

