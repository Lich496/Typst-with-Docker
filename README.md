# Typst with Docker

## Features

Add Typst Language support.

Build `.typ` file with typst on Docker Container.

## Requirements

Docker is installed in your environment and Typst image shold be pulled.
Here is recommended Dockerfile.

```dockerfile
FROM ghcr.io/typst/typst:latest

RUN apk --update add fontconfig

COPY fonts /usr/share/fonts

WORKDIR /data
```

Note that when comppiling, the directory your typst file is in will be mounted to `/data/`.

## Extension Settings

This extension contributes the following settings:

* `typst-with-docker.image`: Which docker image to use
* `typst-with-docker.build.run`: When to build typst file
  - `onType`(default)
  - `onSave`
  - `onBuild`

## Release Notes

### 0.0.1

Initial build