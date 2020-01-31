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
fly -t local unpause-pipeline -p example
```

### Destroy pipeline

```shell
fly -t local destroy-pipeline -p example
```


### Pipeline

```shell
fly hijack -t local -j example/test
```

# Extend Cocnourse CI

- Developing a Custom Concourse Resource https://content.pivotal.io/blog/developing-a-custom-concourse-resource

