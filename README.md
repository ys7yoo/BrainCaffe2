# BrainCaffe2
Info on installing Caffe 2

# Installation
Basically, follow official instruction [here](https://caffe2.ai/docs/getting-started.html?platform=mac&configuration=prebuilt) (with some modifications).

## System libraries

```
sudo apt-get update
sudo apt-get install -y --no-install-recommends \
      build-essential \
      git \
      libgoogle-glog-dev \
      libgtest-dev \
      libiomp-dev \
      libleveldb-dev \
      liblmdb-dev \
      libopencv-dev \
      libopenmpi-dev \
      libsnappy-dev \
      libprotobuf-dev \
      openmpi-bin \
      openmpi-doc \
      protobuf-compiler \
      libgflags-dev \
      cmake
```

## Python packages

```
pip3 install --user \
      future \
      numpy \
      protobuf \
      typing \
      hypothesis \
      pyyaml
```
## Build from source
Under `~/src`, run the following:
```
git clone https://github.com/pytorch/pytorch.git && cd pytorch
git submodule update --init --recursive
python setup.py install
```




### Alternatively, use [Docker from Nvidia](https://docs.nvidia.com/deeplearning/dgx/caffe2-release-notes/rel_18.08.html#rel_18.08)
