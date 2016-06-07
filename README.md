FriendsOfAnsible.kibana
=======================

[![Build Status](https://travis-ci.org/FriendsOfAnsible/ansible-role-kibana.svg?branch=master)](https://travis-ci.org/FriendsOfAnsible/ansible-role-kibana)

Simple role to provision Kibana >= 4.5.x

Requirements
------------

Ansible >= 1.9

Role Variables
--------------

```yaml
- vars:
  kibana_version: "4.5" # kibana version to install

  # debian / ubuntu apt variables
  apt_key_url: https://packages.elastic.co/GPG-KEY-elasticsearch # url for the apt repo key
  apt_repo: "deb http://packages.elastic.co/kibana/{{ kibana_version }}/debian stable main" # apt repo to install kibana from

  node_options: "--max-old-space-size=250" # NodeJS options, by default limiting the memory node will consume

  # kibana config
  kibana_port: 5601 # The port kibana listens to
  kibana_host: "0.0.0.0" # The host to bind the server to.
  elasticsearch_url: "http://localhost:9200" # Elasticsearch host that will be used by Kibana
  kibana_index: ".kibana" # Elasticsearch index where kibana will store its config
```

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - FriendsOfAnsible.kibana
```         

License
-------

MIT
