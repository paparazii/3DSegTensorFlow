Readme:
===================================================================
I use python3.6 and latest Tensorflow source version (master branch at August 3th, 2017).

python3 at: /usr/bin/python3

pathon3 lib: /usr/local/lib/python3.6/site-packages

====================================================================
tensorflow configure process:
[putamen:~/Projects/tensorflow] hxie1% ./configure
WARNING: Running Bazel server needs to be killed, because the startup options are different.
Please specify the location of python. [Default is /usr/bin/python]:  /usr/bin/python3
Found possible Python library paths:
/Library/Python/2.7/site-packages
Please input the desired Python library path to use.  Default is /Library/Python/2.7/site-packages:   /usr/local/lib/python3.6/site-packages
Do you wish to build TensorFlow with Google Cloud Platform support? [y/N]: n
No Google Cloud Platform support will be enabled for TensorFlow.

Do you wish to build TensorFlow with Hadoop File System support? [y/N]: n
No Hadoop File System support will be enabled for TensorFlow.

Do you wish to build TensorFlow with XLA JIT support? [y/N]: n
No XLA JIT support will be enabled for TensorFlow.

Do you wish to build TensorFlow with VERBS support? [y/N]: n
No VERBS support will be enabled for TensorFlow.

Do you wish to build TensorFlow with OpenCL support? [y/N]: n
No OpenCL support will be enabled for TensorFlow.

Do you wish to build TensorFlow with CUDA support? [y/N]: n
No CUDA support will be enabled for TensorFlow.

Do you wish to build TensorFlow with MPI support? [y/N]: n
No MPI support will be enabled for TensorFlow.

Please specify optimization flags to use during compilation when bazel option "--config=opt" is specified [Default is -march=native]:
Add "--config=mkl" to your bazel command to build with MKL support.
Please note that MKL on MacOS or windows is still not supported.
If you would like to use a local MKL instead of downloading, please set the environment variable "TF_MKL_ROOT" every time before build.
Configuration finished
[putamen:~/Projects/tensorflow] hxie1%

============================================================


Bazel compile:
bazel build --config=opt //tensorflow/tools/pip_package:build_pip_package

==============================================================
Generate pip3 wheel:
[putamen:~/Projects/tensorflow] hxie1% ./bazel-bin/tensorflow/tools/pip_package/build_pip_package ~/temp/tensorflow_pkg

==============================================================

Install wheel:
sudo -H pip3 install ~/temp/tensorflow_pkg/tensorflow-1.3.0rc1-cp36-cp36m-macosx_10_12_x86_64.whl

=========================================