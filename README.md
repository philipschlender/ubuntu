# Ubuntu

## Introduction

Ubuntu is a docker image based on [Ubuntu](https://ubuntu.com/). It includes some handy additions like basic packages, preset time zone and user.

## How to use

### Build

```bash
docker build --file docker/Dockerfile --tag philipschlender/ubuntu:latest .
```

### Run

```bash
docker run --interactive --name ubuntu --rm --tty philipschlender/ubuntu:latest
```

### Push

```bash
docker push philipschlender/ubuntu:latest
```
