# Tensorflow GPU Base

This is derived from the tensorflow
[gpu.Dockerfile](https://raw.githubusercontent.com/tensorflow/tensorflow/02956a52930bea96f57401d39a834e13047bad9a/tensorflow/tools/dockerfiles/dockerfiles/gpu.Dockerfile).
The only difference is that it does not setup python or `pip install tensorflow`,
since we want to be able to install that ourselves, possibly in a conda
environment rather than in the default python environment.

See also [https://www.tensorflow.org/install/docker](https://www.tensorflow.org/install/docker).
