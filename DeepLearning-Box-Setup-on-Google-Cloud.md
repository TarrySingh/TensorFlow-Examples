Go to 

Full logical steps to script
===========================


00:02 https://cloud.google.com/

00:06 https://www.youtube.com/watch?v=IEa8hIvkto0

00:18 https://console.cloud.google.com/compute/quotas

00:47 https://console.cloud.google.com/networking/firewalls/list

00:58 tcp:8888; udp:8888

01:15 https://console.cloud.google.com/compute/instances

02:27 https://cloud.google.com/compute/docs/gpus/add-gpus

02:34 https://pastebin.com/raw/U7fQFiZd

02:50 https://www.youtube.com/watch?v=YoBEGQD3LCc

03:07 sudo apt-get update

03:11 https://www.tensorflow.org/install/install_linux#nvidia_requirements_to_run_tensorflow_with_gpu_support

03:22 https://developer.nvidia.com/rdp/form/cudnn-download-survey

03:48 https://developer.nvidia.com/cudnn

04:15 sudo apt-get install ipython

04:22 sudo apt-get install python3-pip

04:32 sudo pip3 install jupyter

04:42 sudo jupyter notebook --ip 0.0.0.0 --port 8888 --allow-root

05:35 https://www.scipy.org/install.html

05:37 sudo pip3 install numpy scipy matplotlib ipython jupyter pandas sympy nose

05:40 https://alliseesolutions.wordpress.com/2016/09/08/install-gpu-tensorflow-from-sources-w-ubuntu-16-04-and-cuda-8-0-rc/

05:45 sudo apt-get install openjdk-8-jdk git python-dev python3-dev python-numpy python3-numpy python-six python3-six build-essential python-pip python3-pip python-virtualenv swig python-wheel python3-wheel libcurl3-dev libcupti-dev

05:55 tar -xzvf cudnn-8.0-linux-x64-v5.1.tgz

06:02 sudo cp cuda/include/cudnn.h /usr/local/cuda/include

06:04 sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64

06:07 sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*

06:12 nano ~/.bashrc

06:17 add these lines:

export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda/lib64:/usr/local/cuda/extras/CUPTI/lib64"

export CUDA_HOME=/usr/local/cuda

06:21 source ~/.bashrc

06:27 echo "deb [arch=amd64] http://storage.googleapis.com/bazel-apt stable jdk1.8" | sudo tee /etc/apt/sources.list.d/bazel.list

06:29 curl https://bazel.build/bazel-release.pub.gpg | sudo apt-key add -

06:31 sudo apt-get update

06:33 sudo apt-get install bazel

06:35 sudo apt-get upgrade bazel

06:38 git clone https://github.com/tensorflow/tensorflow

06:41 cd ~/tensorflow

06:43 git checkout r1.0

06:47 ./configure

06:59 /usr/bin/python3.5

(press enter until you get to "Please input the desired Python library path to use.")

07:11 /usr/local/lib/python3.5/dist-packages

(press enter once, then you should be at "Do you wish to build TensorFlow with CUDA support?" to which you can answer "y")

07:16 y

07:24 3.7

07:30 bazel build --config=opt --config=cuda //tensorflow/tools/pip_package:build_pip_package

07:35 bazel-bin/tensorflow/tools/pip_package/build_pip_package /tmp/tensorflow_pkg

07:41 sudo pip3 install /tmp/tensorflow_pkg/tensorflow[PRESS TAB TO COMPLETE FILENAME]

(Now quit the SSH window and come back)

'python3

import tensorflow as tf

sess = tf.InteractiveSession()

sess.close()


it clone https://github.com/llSourcell/How_to_do_style_transfer_in_tensorflow

sudo jupyter notebook --ip 0.0.0.0 --port 8888 --allow-root

Common problems / silly mistakes you may end up making and fixes

1. 


