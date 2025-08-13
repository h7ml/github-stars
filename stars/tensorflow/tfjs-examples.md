---
project: tfjs-examples
stars: 6738
description: Examples built with TensorFlow.js
url: https://github.com/tensorflow/tfjs-examples
---

TensorFlow.js Examples
======================

This repository contains a set of examples implemented in TensorFlow.js.

Each example directory is standalone so the directory can be copied to another project.

Overview of Examples
====================

Example name

Demo link

Input data type

Task type

Model type

Training

Inference

API type

Save-load operations

abalone-node

Numeric

Loading data from local file and training in Node.js

Multilayer perceptron

Node.js

Node.js

Layers

Saving to filesystem and loading in Node.js

addition-rnn

🔗

Text

Sequence-to-sequence

RNN: SimpleRNN, GRU and LSTM

Browser

Browser

Layers

addition-rnn-webworker

Text

Sequence-to-sequence

RNN: SimpleRNN, GRU and LSTM

Browser: Web Worker

Browser: Web Worker

Layers

angular-predictive-prefetching

Numeric

Multiclass predictor

DNN

Browser: Service Worker

Layers

baseball-node

Numeric

Multiclass classification

Multilayer perceptron

Node.js

Node.js

Layers

boston-housing

🔗

Numeric

Regression

Multilayer perceptron

Browser

Browser

Layers

cart-pole

🔗

Reinforcement learning

Policy gradient

Browser

Browser

Layers

IndexedDB

chrome-extension

Image

(Deploying TF.js in Chrome extension)

Convnet

Browser

custom-layer

🔗

(Defining a custom Layer subtype)

Browser

Layers

data-csv

🔗

Building a tf.data.Dataset from a remote CSV

data-generator

🔗

Building a tf.data.Dataset using a generator

Regression

Browser

Browser

Layers

date-conversion-attention

🔗

Text

Text-to-text conversion

Attention mechanism, RNN

Node.js

Browser and Node.js

Layers

Saving to filesystem and loading in browser

electron

Image

(Deploying TF.js in Electron-based desktop apps)

Convnet

Node.js

fashion-mnist-vae

Image

Generative

Variational autoencoder (VAE)

Node.js

Browser

Layers

Export trained model from tfjs-node and load it in browser

interactive-visualizers

Image

Multiclass classification, object detection, segmentation

Browser

iris

🔗

Numeric

Multiclass classification

Multilayer perceptron

Browser

Browser

Layers

iris-fitDataset

🔗

Numeric

Multiclass classification

Multilayer perceptron

Browser

Browser

Layers

jena-weather

🔗

Sequence

Sequence-to-prediction

MLP and RNNs

Browser and Node

Browser

Layers

lstm-text-generation

🔗

Text

Sequence prediction

RNN: LSTM

Browser

Browser

Layers

IndexedDB

mnist

🔗

Image

Multiclass classification

Convolutional neural network

Browser

Browser

Layers

mnist-acgan

🔗

Image

Generative Adversarial Network (GAN)

Convolutional neural network; GAN

Node.js

Browser

Layers

Saving to filesystem from Node.js and loading it in the browser

mnist-core

🔗

Image

Multiclass classification

Convolutional neural network

Browser

Browser

Core (Ops)

mnist-node

Image

Multiclass classification

Convolutional neural network

Node.js

Node.js

Layers

Saving to filesystem

mnist-transfer-cnn

🔗

Image

Multiclass classification (transfer learning)

Convolutional neural network

Browser

Browser

Layers

Loading pretrained model

mobilenet

🔗

Image

Multiclass classification

Convolutional neural network

Browser

Layers

Loading pretrained model

polynomial-regression

🔗

Numeric

Regression

Shallow neural network

Browser

Browser

Layers

polynomial-regression-core

🔗

Numeric

Regression

Shallow neural network

Browser

Browser

Core (Ops)

quantization

Various

Demonstrates the effect of post-training weight quantization

Various

Node.js

Node.js

Layers

sentiment

🔗

Text

Sequence-to-binary-prediction

LSTM, 1D convnet

Node.js or Python

Browser

Layers

Load model from Keras and tfjs-node

simple-object-detection

🔗

Image

Object detection

Convolutional neural network (transfer learning)

Node.js

Browser

Layers

Export trained model from tfjs-node and load it in browser

snake-dqn

🔗

Reinforcement learning

Deep Q-Network (DQN)

Node.js

Browser

Layers

Export trained model from tfjs-node and load it in browser

translation

🔗

Text

Sequence-to-sequence

LSTM encoder and decoder

Node.js or Python

Browser

Layers

Load model converted from Keras

tsne-mnist-canvas

Dimension reduction and data visualization

tSNE

Browser

Browser

Core (Ops)

webcam-transfer-learning

🔗

Image

Multiclass classification (transfer learning)

Convolutional neural network

Browser

Browser

Layers

Loading pretrained model

website-phishing

🔗

Numeric

Binary classification

Multilayer perceptron

Browser

Browser

Layers

Dependencies
============

Except for `getting_started`, all the examples require the following dependencies to be installed.

-   Node.js version 8.9 or higher
-   NPM cli OR Yarn

How to build an example
-----------------------

`cd` into the directory

If you are using `yarn`:

cd mnist-core
yarn
yarn watch

If you are using `npm`:

cd mnist-core
npm install
npm run watch

### Details

The convention is that each example contains two scripts:

-   `yarn watch` or `npm run watch`: starts a local development HTTP server which watches the filesystem for changes so you can edit the code (JS or HTML) and see changes when you refresh the page immediately.
    
-   `yarn build` or `npm run build`: generates a `dist/` folder which contains the build artifacts and can be used for deployment.
    

Contributing
------------

If you want to contribute an example, please reach out to us on Github issues before sending us a pull request as we are trying to keep this set of examples small and highly curated.

### Running Presubmit Tests

Before you send a pull request, it is a good idea to run the presubmit tests and make sure they all pass. To do that, execute the following commands in the root directory of tfjs-examples:

yarn
yarn presubmit

The `yarn presubmit` command executes the unit tests and lint checks of all the exapmles that contain the `yarn test` and/or `yarn lint` scripts. You may also run the tests for individual exampls by cd'ing into their respective subdirectory and executing `yarn`, followed by `yarn test` and/or `yarn lint`.
