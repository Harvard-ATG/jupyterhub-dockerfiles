# Jupyterhub Dockerfiles

This repository contains Dockerfiles for Jupyterhub. 

## Tensorflow GPU Base Image

**To use this image:**

```
$ docker pull harvardat/tensorflow-gpu-base:latest
```

**Description:**

The `tensorflow-gpu-base` image is based on the [official GPU-enabled tensorflow docker image](https://www.tensorflow.org/install/docker) and is intended to be a drop-in replacement. The GPU-enabled version handles the installation of the [CUDA Toolkit](https://developer.nvidia.com/cuda-toolkit) that is required for GPU computing as well as other required libraries.

While we could use the official image, we would like to handle the installation of the python environment and `tensorflow` separately (such as in a `conda` environment), so our image is more or less the same except it omits the last part the configures python and does a `pip install tensorflow`. So this gives us a base image with everything we need to do that.

See the official [gpu.Dockerfile](https://raw.githubusercontent.com/tensorflow/tensorflow/02956a52930bea96f57401d39a834e13047bad9a/tensorflow/tools/dockerfiles/dockerfiles/gpu.Dockerfile) for reference. 

## Automated Builds

Github Actions are setup to automatically build and push images to https://hub.docker.com/u/harvardat. The asusmption is that there is no sensitive information being added to these images.