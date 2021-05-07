# quansight-conda-linux-anvil

These are experiments to be able to adapt the following Docker images to run in a QHub JupyterLab environment:

- [condaforge/linux-anvil-cos7-x86_64](https://hub.docker.com/r/condaforge/linux-anvil-cos7-x86_64)
- [condaforge/linux-anvil-aarch64](https://hub.docker.com/r/condaforge/linux-anvil-aarch64)

This is for [QHub Issue 551](https://github.com/Quansight/qhub/issues/551).

To try out (using the cos7-x86_64 base as default):

```
git clone https://github.com/Quansight/quansight-conda-linux-anvil
cd quansight-conda-linux-anvil
docker build -t quansight/conda-linux-anvil-cos7-x86_64 .
```

for the aarch64 version try:
```
docker build --build-arg BASE_CONTAINER=condaforge/linux-anvil-aarch64:latest -t quansight/conda-linux-anvil-aarch64 .
```

The Dockerfile and supporting files were created by attempting to merge components of [jupyter/base-notebook](https://github.com/jupyter/docker-stacks/blob/master/base-notebook/Dockerfile) on top of the base condaforge image.

As of 7 May 2021 I have tried only the cos7-x86_64 version which you can try on Docker Hub as [danlester/q-conda-linux-anvil-cos7-x86_64](https://hub.docker.com/r/danlester/q-conda-linux-anvil-cos7-x86_64). This seems to work as a JupyterLab image (I've only tried via DockerSpawner) but not sure about the original conda linux bits.

