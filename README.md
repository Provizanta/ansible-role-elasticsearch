Elasticsearch
=========

Elasticsearch installation and configuration.

Requirements
------------

None

Role Variables
--------------
These defaults are set in defaults/main.yml:

    version: 6

    jvm_options:
      heap_space: "1g"

    configuration:
      cluster:
        name: "{{ inventory_hostname }}"
        remote.connect: false
      node:
        name: "{{ inventory_hostname }}"
        master: true
        data: true
        ingest: true
      discovery.zen:
        ping.unicast.hosts: "{{ ['127.0.0.1'] | to_json }}"
        minimum_master_nodes: 1
      path:
        logs: "/var/log/elasticsearch"
        data: "/var/lib/elasticsearch"
      bootstrap.memory_lock: true
      network.host: "127.0.0.1"
      http.port: "9200"

    service:
      enabled: true
      state: started

Dependencies
------------

None

Example Playbook
----------------

    - hosts: servers
      roles:
        - role: elasticsearch
          vars:
            jvm_options:
              heap_space: "2g"

License
-------

MIT

Author Information
------------------

Tibor Csóka
