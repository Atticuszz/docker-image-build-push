# docker-image-build-push
> esay version for qucikly build and publish to docker hub

> make sure have Dockerfile in `./`
1. config `DOCKER_HUB_USERNAME` and `DOCKER_HUB_ACCESS_TOKEN` in github action repo secrets
2. config your `image_name` follow the proper format like `"username/image_name:tags"`
```yml
name: CI/CD
on:
  push:
    branches:
      - main
  pull_request:
  workflow_dispatch:

  docker-build:
    runs-on: ubuntu-latest
    steps:
      - name: Build and Push Docker Image
        uses: Atticuszz/docker-image-build-push@v0.0.1
        with:
          docker_hub_username: ${{ secrets.DOCKER_HUB_USERNAME }}
          docker_hub_access_token: ${{ secrets.DOCKER_HUB_ACCESS_TOKEN }}
          image_name: "username/image_name:latest"
```
