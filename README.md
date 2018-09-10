ansible-role-k-link
===================

This repository contains the ansible roles for setting up a complete K-Link
Network as a docker-compose service, consisting of all neccessary
components:

- **K-Search engine** for indexing and searching through text
- **K-Search** for providing an external API to interface with the search
- **K-Link** as a public facing website, displaying general information
- **K-Link-Registry** for fine-grained access management
- **Mariadb** as a data store

Requirements
------------

Docker and traefik must be installed on the host machine, using the
respective roles.

Configuration Variables
-----------------------

```yaml
k_links: [] # K-links is an array of entries, so that multiple instances
            # may be set up at once.

k_links:
  domain.example.org:
    path: "" # location of the docker service files
    data: "" # location where the files are persisted to
    conf: "" # location of the configuration files
    images:
      # image used for the search service
      k_search: ""
      # image used for solr
      solr: ""
      # image used for the k-link-registry service
      registry: ""
```

Example configuration
---------------------

```yaml
k_links:
  klink.example.com:
    path: "/home/user/deploy/k-link/klink-example-com"
    data: "/data/k-link/klink-example-com"
    images:
      solr: "docker.klink.asia/images/k-search-engine:0.4.0"
      k_search: "docker.klink.asia/images/k-search:3.2.0-1"
      registry: "docker.klink.asia/main/k-link-registry:squash"

```

Dependencies
------------

None

License
-------

MIT
