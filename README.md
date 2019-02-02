# BrainCaffe2
Info on installing Caffe 2

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
pip3 install --user \
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
git submodule update --init --recursive
python3 setup.py install
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

### Alternatively, use [Docker from Nvidia](https://docs.nvidia.com/deeplearning/dgx/caffe2-release-notes/rel_18.08.html#rel_18.08)
