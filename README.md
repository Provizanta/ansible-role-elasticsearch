Ansible role: Elasticsearch
=========

Elasticsearch installation and configuration.

Requirements
------------

None

Role Variables
--------------
These variables are defined in [defaults/main.yml](./defaults/main.yml):

    elk_version: 6

    elk_elasticsearch_service:
      enabled: true
      state: started

Other variables that can be set:

    elk_elasticsearch_log4j2:               # string, the entire file contents

    elk_elasticsearch_configuration:        # the entire Elasticsearch YAML configuration

    elk_elasticsearch_jvm_options:
      heap_space: "1g"

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: elasticsearch
          vars:
            elk_elasticsearch_jvm_options:
              heap_space: "2g"

License
-------

MIT

Author Information
------------------

Tibor Csóka
