# js.graylog2/README.md

## Execution Requirements
- Tested on CentOS 7

## Role Variables

The following variables can be overridden:
* `graylog2_cluster_name`: Default: "graylog"
* `graylog2_root_email`: Default: "graylogadmin@example.com"
* `graylog2_admin_password`: Default: "graylog"
* `graylog2_root_timezone`: Default: "Europe/Zurich"
* `graylog2_allow_highlighting`: Default: true
* `graylog2_dashboard_widget_default_cache_time`: Default: 60s

* `graylog2_transport_email_enabled`: Default: false
* `graylog2_transport_email_hostname`: Default: mail.example.com
* `graylog2_transport_email_port`: Default: 587
* `graylog2_transport_email_use_auth`: Default: true
* `graylog2_transport_email_use_tls`: Default: true
* `graylog2_transport_email_use_ssl`: Default: true
* `graylog2_transport_email_auth_username`: Default: "you@example.com"
* `graylog2_transport_email_auth_password`:  Default: secret
* `graylog2_transport_email_subject_prefix`: Default: "[graylog]"
* `graylog2_transport_email_from_email`: Default: "graylog@example.com"
* `graylog2_transport_email_web_interface_url`: Default: "http://{{ansible_default_ipv4.address}}:9000"

* `graylog2_password_secret`: Default: "AU43aOqqswYJJyQSICrF8UzpQ2D3Q9YY5pzA6Gw2oZIdQqoR2Fibr2GnTcwRuneVfejp4qzgAcHOv0Ode64dL9BkzptsLmGE"
   generate: pwgen -s 96 1

* `graylog2_repo_graylog_rpm`: Default: https://packages.graylog2.org/repo/packages/graylog-2.2-repository_latest.rpm

* `graylog2_repo_elasticsearch_url`: Default: https://packages.elastic.co/elasticsearch/2.x/centos
* `graylog2_repo_elasticsearch_key`: Default: https://packages.elastic.co/GPG-KEY-elasticsearch

* `graylog2_repo_mongodb_url`: Default: https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/3.2/$basearch/
* `graylog2_repo_mongodb_key`: Default: https://www.mongodb.org/static/pgp/server-3.2.asc


## Features
* Automatic restart of graylog service if config file has changed

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
https://opensource.org/licenses/MIT   
Copyright (c) Chris Ruettimann <chris@bitbull.ch>  

