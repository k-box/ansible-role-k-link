# K-Link

## Configuration Variables
```yaml
  k_links:
    domain.example.org:
      path: "" # location of the docker service files
      data: "" # location of the data path
      conf: "" # location of the configuration files
      images:
        # image used for the search service
        k_search: ""
        # image used for solr
        solr: ""
        # image used for the k-link-registry service
        registry: ""
        #
```

## Example configuration
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
