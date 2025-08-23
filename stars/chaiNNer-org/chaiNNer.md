---
project: chaiNNer
stars: 5265
description: A node-based image processing GUI aimed at making chaining image processing tasks easy and customizable. Born as an AI upscaling application, chaiNNer has grown into an extremely flexible and powerful programmatic image processing application.
url: https://github.com/chaiNNer-org/chaiNNer
---

chaiNNer
========

A node-based image processing GUI aimed at making chaining image processing tasks easy and customizable. Born as an AI upscaling application, chaiNNer has grown into an extremely flexible and powerful programmatic image processing application.

ChaiNNer gives you a level of customization of your image processing workflow that very few others do. Not only do you have full control over your processing pipeline, you can do incredibly complex tasks just by connecting a few nodes together.

ChaiNNer is also cross-platform, meaning you can run it on Windows, MacOS, and Linux.

For help, suggestions, or just to hang out, you can join the chaiNNer Discord server

Remember: chaiNNer is still a work in progress and in alpha. While it is slowly getting more to where we want it, it is going to take quite some time to have every possible feature we want to add. If you're knowledgeable in TypeScript, React, or Python, feel free to contribute to this project and help us get closer to that goal.

Note: As of right now, chaiNNer is not under active development. This may resume in the future, but at the moment there is no active dev work aside from community contributions via PRs.

Installation
------------

Download the latest release from the Github releases page and run the installer best suited for your system. Simple as that.

You don't even need to have Python installed, as chaiNNer will download an isolated integrated Python build on startup. From there, you can install all the other dependencies via the Dependency Manager.

If you do wish to use your system Python installation still, you can turn the system Python setting on. However, it is much more recommended to use integrated Python. If you do wish to use your system Python, we recommend using Python 3.11, but we try to support 3.8, 3.9, and 3.10 as well.

If you'd like to test the latest changes and tweaks, try out our nightly builds

How To Use
----------

### Basic Usage

While it might seem intimidating at first due to all the possible options, chaiNNer is pretty simple to use. For example, this is all you need to do in order to perform an upscale:

Before you get to this point though, you'll need to install one of the neural network frameworks from the dependency manager. You can access this via the button in the upper-right-hand corner. ChaiNNer offers support for PyTorch (with select model architectures), NCNN, and ONNX. For Nvidia users, PyTorch will be the preferred way to upscale. For AMD users, NCNN will be the preferred way to upscale.

All the other Python dependencies are automatically installed, and chaiNNer even carries its own integrated Python support so that you do not have to modify your existing Python configuration.

Then, all you have to do is drag and drop (or double click) node names in the selection panel to bring them into the editor. Then, drag from one node handle to another to connect the nodes. Each handle is color-coded to its specific type, and while connecting will show you only the compatible connections. This makes it very easy to know what to connect where.

Once you have a working chain set up in the editor, you can press the green "run" button in the top bar to run the chain you have made. You will see the connections between nodes become animated, and start to un-animate as they finish processing. You can stop or pause processing with the red "stop" and yellow "pause" buttons respectively.

Don't forget, there are plenty of non-upscaling tasks you can do with chaiNNer as well!

### Tips & Tricks

To select multiple nodes, hold down shift and drag around all the nodes you want to be selected. You can also select an individual node by just clicking on it. When nodes are selected, you can press backspace or delete to delete them from the editor.

To perform batch processing on a folder of images, use the "Load Images" node. To process videos, use the "Load Video" node. It's important to note however that you cannot use both "Load Images" and "Load Video" nodes (or any two nodes that perform batch iteration) together in a chain. You can however combine the output (collector) nodes in the chain, for example using "Save Image" with "Load Video", and "Save Video" with "Load Images".

You can right-click in the editor viewport to show an inline nodes list to select from. You also can get this menu by dragging a connection out to the editor rather than making an actual connection, and it will show compatible nodes to automatically create a connection with.

### Helpful Resources

-   Kim's chaiNNer Templates
    -   A collection of useful chain templates that can quickly get you started if you are still new to using chaiNNer.
-   OpenModelDB Model Database
    -   A nice collection of Super-Resolution models that have been trained by the community.
-   Interactive Visual Comparison of Upscaling Models
    -   An online comparison of different models. The author also provides a list of favorites.

Compatibility Notes
-------------------

-   MacOS versions 10.x and below are not supported.
    
-   Windows versions 8.1 and below are also not supported.
    
-   Apple Silicon Macs should support almost everything. Although, ONNX only supports the CPU Execution Provider, and NCNN sometimes does not work properly.
    
-   Some NCNN users with non-Nvidia GPUs might get all-black outputs. I am not sure what to do to fix this as it appears to be due to the graphics driver crashing as a result of going out of memory. If this happens to you, try manually setting a tiling amount.
    
-   To use the Clipboard nodes, Linux users need to have xclip or, for wayland users, wl-copy installed.
    

GPU Support
-----------

For PyTorch inference, only Nvidia GPUs are officially supported. If you do not have an Nvidia GPU, you will have to use PyTorch in CPU mode. This is because PyTorch only supports Nvidia's CUDA. MacOS users on Apple Silicon Macs can also take advantage of PyTorch's MPS mode, which should work with chaiNNer.

If you have an AMD or Intel GPU that supports NCNN however, chaiNNer now supports NCNN inference. You can use any existing NCNN .bin/.param model files (only ESRGAN-related SR models have been tested), or use chaiNNer to convert a PyTorch or ONNX model to NCNN.

For NCNN, make sure to select which GPU you want to use in the settings. It might be defaulting to your integrated graphics!

For Nvidia GPUs, ONNX is also an option to be used. ONNX will use CPU mode on non-Nvidia GPUs, similar to PyTorch.

Model Architecture Support
--------------------------

ChaiNNer currently supports a limited amount of neural network architectures. More architectures will be supported in the future.

### PyTorch

As of v0.21.0, chaiNNer uses our new package called Spandrel to support Pytorch model architectures. For a list of what's supported, check out the list there.

### NCNN

#### Single Image Super Resolution

-   Technically, almost any SR model should work assuming they follow a typical CNN-based SR structure. However, I have only tested with ESRGAN (and its variants) and with Waifu2x.

### ONNX

#### Single Image Super Resolution

-   Similarly to NCNN, technically almost any SR model should work assuming they follow a typical CNN-based SR structure. However, I have only tested with ESRGAN.

#### Background Removal

-   u2net | u2net, u2netp, u2net\_cloth\_seg, u2net\_human\_seg, silueta
-   isnet | isnet

Troubleshooting
---------------

For troubleshooting information, view the troubleshooting document.

Building chaiNNer Yourself
--------------------------

I provide pre-built versions of chaiNNer here on GitHub. However, if you would like to build chaiNNer yourself, simply run `npm install` (make sure that you have at least npm v7 installed) to install all the nodejs dependencies, and `npm run make` to build the application.

FAQ
---

For FAQ information, view the FAQ document.
