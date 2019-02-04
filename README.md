# BrainCaffe2
Info on building Caffe 2 from source

# Install Caffe2 on Ubuntu (16.04 with GPUs)
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
sudo pip3 install \
      future \
      numpy \
      protobuf \
      typing \
      hypothesis \
      pyyaml \
      pydot
```
## Build from source
Under `~/src`, run the following:
```
git clone https://github.com/pytorch/pytorch.git && cd pytorch
git checkout db5d313
git submodule update --init --recursive
CC=/usr/bin/gcc-5 CXX=/usr/bin/g++-5 python3 setup.py install
```

## test 
Check whether build was successful or not
```
python3 -c 'from caffe2.python import core' 2>/dev/null && echo "Success" || echo "Failure"
```

Test a module.
```
python3 caffe2/python/operator_test/activation_ops_test.py
```


## Detectron installation

```
pip3 install -r requirements.txt  --user
```



# Install Caffe2 on OSX (10.14 without GPUs)
## Install Macports
* https://www.macports.org/install.php
* https://distfiles.macports.org/MacPorts/MacPorts-2.5.4-10.14-Mojave.pkg

## Install base packages using Macports
```
sudo port install cmake openmpi gflags
```


# Alternatively, use [Docker from Nvidia](https://docs.nvidia.com/deeplearning/dgx/caffe2-release-notes/rel_18.08.html#rel_18.08)
