# incident-playground

http://localhost:3000/

## Installl Framework
### Windows
Buffalo can be installed using the [Scoop](https://scoop.sh/) package manager:
```
C:\> scoop install buffalo
C:\> scoop install gcc
```

### Homebrew (macOS)
Buffalo can be installed using the [Homebrew](https://brew.sh/) package manager:
```
$ brew install gobuffalo/tap/buffalo
```

## Database settings

### Start Postgres
```
$ docker-compose up -d
```

### Install Pop 
Windows:
```
C:\> go install github.com/gobuffalo/pop/v6/soda@latest
```

Homebrew (macOS):
```
$ brew install gobuffalo/tap/pop
```

### Create databases

```
$ buffalo pop create -a

pop v6.0.1

[POP] 2022/05/26 00:43:06 info - create incident_playground_production (postgres://postgres:postgres@127.0.0.1:5432/incident_playground_production?sslmode=disable)
[POP] 2022/05/26 00:43:08 info - created database incident_playground_production
[POP] 2022/05/26 00:43:08 info - create incident_playground_development (postgres://postgres:postgres@0.0.0.0:5432/incident_playground_development?)
[POP] 2022/05/26 00:43:10 info - created database incident_playground_development
[POP] 2022/05/26 00:43:10 info - create incident_playground_test (postgres://postgres:postgres@127.0.0.1:5432/incident_playground_test?sslmode=disable)
[POP] 2022/05/26 00:43:11 info - created database incident_playground_test
```

### How to access the local databases

```
$ docker exec -it incident-playground-db bin/bash

Container...
$ psql -U postgres

List of databases...
postgres=# \l
```

## Not Required
### Project Create

```
$ buffalo new incident-playground --module github.com/aiit2022-pbl-okuhara/incident-playground --db-type postgres
```
