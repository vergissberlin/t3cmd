# Concourse example

## Presentantion

- Vorstellung
- Überblick CI
- Wann setzt ich ich Concourse CI ein
- Gemeinsam Concourse starten
- Concourse Erweitern


## Usage

```shell
docker-compose up -d
```

### Set the pipeline

```shell
fly login -t local -c http://0.0.0.0:8010
fly set-pipeline -t local -p example -c pipeline.yml -n
fly -t local unpause-pipeline -p mqtt-resource
```

### Destroy pipeline

```shell
fly -t local destroy-pipeline -p mqtt-resource
```

## Debug

Set ``debug: true`` in the pipeline at the source configuration part.

```yml
resource_types:
- name: mqtt-resource
  type: docker-image
  source:
    repository: vergissberlin/mqtt-resource
    tag: development
    debug: true
```

### Pipeline

```shell
fly hijack -t local -j mqtt-resource/example
```

# Extend Cocnourse CI

- Developing a Custom Concourse Resource https://content.pivotal.io/blog/developing-a-custom-concourse-resource

