---
layout: default
title: JNI libraries
nav_order: 6
parent: k-NN
has_children: false
---

# JNI libraries

To integrate [*nmslib*'s](https://github.com/nmslib/nmslib/) and [*faiss*'s](https://github.com/facebookresearch/faiss/) Approximate k-NN functionality (implemented in C++) into the k-NN plugin (implemented in Java), we created a Java Native Interface, which lets the k-NN plugin make calls to the native libraries. We create 3 libraries: `libopensearchknn_nmslib`, the JNI library that interfaces with nmslib, `libopensearchknn_faiss`, the JNI library that interfaces with faiss, and `libopensearchknn_common`, a library containing common shared functionality between native libraries.

The libraries `libopensearchknn_faiss` and `libopensearchknn_nmslib` are lazily loaded when they are first called in the plugin. This means that if you are only planning on using one of the libraries, the plugin never loads the other library.

To build the libraries from source, refer to the [DEVELOPER_GUIDE](https://github.com/opensearch-project/k-NN/blob/main/DEVELOPER_GUIDE.md).

For more information about JNI, see [Java Native Interface](https://en.wikipedia.org/wiki/Java_Native_Interface) on Wikipedia.
