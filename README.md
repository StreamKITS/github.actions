# Github Actions

Simple Github actions to implement on your NodeJS projects, etc.

## Available actions
### Docker-image
&nbsp;
```yml
name: Docker Image CI

on:
  release:
    types: [published]

jobs:
  build:
    runs-on: ubuntu-latest
    permissions:
      contents: read
      packages: write

    steps:
      - name: Checkout the code
        uses: actions/checkout@v2

      - name: Build docker
        uses: Libertech-FR/lt-actions/docker-image@main
        with:
          context: .
          repository: ${{ github.repository }}
          username: ${{ github.actor }}
          password: ${{ secrets.GITHUB_TOKEN }}
```