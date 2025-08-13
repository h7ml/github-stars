---
project: Tengine-Convert-Tools
stars: 93
description: Tengine Convert Tool supports converting multi framworks' models into tmfile that suitable for Tengine-Lite AI framework.
url: https://github.com/OAID/Tengine-Convert-Tools
---

Tengine Convert Tools
=====================

Introduction
============

Tengine Convert Tool supports converting multi framworks' models into tmfile that suitable for Tengine-Lite AI framework. Since this tool relys on protobuf to resolve proto file of Caffe, ONNX, TensorFlow, TFLite and so on, it can only run under x86 Linux system.

Install dependent libraries
---------------------------

-   For loading caffe model or TensorFlow model.

sudo apt install libprotobuf-dev protobuf-compiler

-   If use the Fedora/CentOS ,use follow command instead.

sudo dnf install protobuf-devel
sudo dnf install boost-devel glog-devel

Build Convert Tool
------------------

mkdir build && cd build
cmake ..
make -j\`nproc\` && make install

Exection File
-------------

-   The exection should be under `./build/install/bin/` named as `convert_tool`.

Run Convert Tool
----------------

### How to use

```
$ ./convert_tool -h
[Convert Tools Info]: optional arguments:
        -h    help            show this help message and exit
        -f    input type      path to input float32 tmfile
        -p    input structure path to the network structure of input model(*.prototxt, *.symbol, *.cfg)
        -m    input params    path to the network params of input model(*.caffemodel, *.params, *.weight, *.pb, *.onnx, *.tflite)
        -o    output model    path to output fp32 tmfile
```

To run the convert tool, running as following command, Note: The command examples are based on `mobilenet` model:

-   Caffe

./install/bin/convert\_tool -f caffe -p mobilenet\_deploy.prototxt -m mobilenet.caffemodel -o mobilenet.tmfile

-   MxNet

./install/bin/convert\_tool -f mxnet -p mobilenet1\_0-symbol.json -m mobilene1\_0-0000.params -o mobileent.tmfile

-   ONNX

./install/bin/convert\_tool -f onnx -m mobilenet.onnx -o mobilenet.tmfile

-   TensorFlow

./install/bin/convert\_tool -f tensorflow -m mobielenet\_v1\_1.0\_224\_frozen.pb -o mobilenet.tmfile

-   TFLITE

./install/bin/convert\_tool -f tflite -m mobielenet.tflite -o mobilenet.tmfile

-   DarkNet: darknet only support for yolov3 model

./install/bin/convert\_tool -f darknet -p yolov3.cfg -m yolov3.weights -o yolov3.tmfile

-   NCNN

./install/bin/convert\_tool -f ncnn -p mobilenet.param -m mobilenet.bin -o mobilenet.tmfile

-   MegEngine

./install/bin/convert\_tool -f megengine -m mobilenet.pkl -o mobilenet.tmfile

-   PaddlePaddle

./install/bin/convert\_tool -f paddle -p inference.pdmodel -m inference.pdiparams -o mobilenetv2\_paddle.tmfile

How to enable MegEngine support\[optional\]
-------------------------------------------

-   First of all, build MegEngine with **DEBUG** mode:

# clone MegEngine
git clone https://github.com/MegEngine/MegEngine.git

# prepare for building
cd MegEngine
./third\_party/prepare.sh
./third\_party/install-mkl.sh
mkdir build && cd build

# build MegEngine with DEBUG mode
cmake .. -DMGE\_WITH\_TEST=OFF -DMGE\_BUILD\_SDK=OFF -DCMAKE\_BUILD\_TYPE=Debug -DCMAKE\_INSTALL\_PREFIX={PREDEFINED\_INSTALL\_PATH}
make -j\`nproc\`
make install
make develop

# export environment
export PYTHONPATH=/path/to/MegEngine/python\_module

# test with python
 python3 -c "import megengine"

-   Build Tengine convert tool

# clone Tengine convert tool
git clone https://github.com/OAID/Tengine-Convert-Tools

# build with MegEngine support
cmake -DBUILD\_MEGENGINE\_SERIALIZER=ON -DMEGENGINE\_INSTALL\_PATH={PREDEFINED\_INSTALL\_PATH} ..
make -j\`nproc\`
make install

-   Serialize your MegEngine model

\# get a pre-trained resnet18 model from MegEngine Model Hub
import megengine.hub
resnet18 \= megengine.hub.load("megengine/models", "resnet18", pretrained\=True)

\# use MegEngine trace to deal with downloaded model
from megengine.jit import trace
import megengine.functional as F

@trace(symbolic\=True)
def pred\_fun(data, \*, net):
    net.eval()
    pred \= net(data)
    \# if model has softmax
    pred\_normalized \= F.softmax(pred)
    return pred\_normalized

\# fill a random input for model
import numpy as np
data \= np.random.random((1, 3, 224, 224)).astype(np.float32)

\# trace and save the model
pred\_fun.trace(data, net\=resnet18)
pred\_fun.dump('new\_model.pkl')

A jupyter notebook was offered for users, check MegEngine.ipynb.

-   Convert MegEngine .pkl model to Tengine .tmfile

./install/bin/convert\_tool -f megengine -m new\_model.pkl -o resnet18.tmfile

How to add self define operator
-------------------------------

-   Adding operator's name defined file under operator/include directory that likes xxx.hpp and xxx\_param.hpp (including operator's params);
-   Adding operator's memory allocation (calculate the memory) under operator/operator directory;
-   Register operator in project operators' registery under operator/operator/plugin/init.cpp file;
-   After adding operator definition, you need to add operator into model serializers, these files are under tools directory. There are multiply framework model serializers, finding file name and .cpp file under that corresponding framwork folder. Following the other operator's definition in that .cpp file.

License
-------

-   Apache 2.0

Tech Forum
----------

-   Github issues
-   QQ groupchat: 829565581
-   Email: Support@openailab.com
-   Tengine Community: http://www.tengine.org.cn/
