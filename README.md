# aws_gpu_deeplearning_setup

YouTube tutorial from Jeremy Howard :

https://www.youtube.com/watch?v=8rjRfW4JM2I

The setup_instance.sh script assumes your .pem file name follows "aws-key-$name.pem" with $name being defined at the top.

If your .pem file name is "aws-key-fast-ai.pem" you can keep the aws-alias.sh file as it is but otherwise the following line needs to be modified :
alias aws-ssh='ssh -i ~/.ssh/aws-key-fast-ai.pem ubuntu@$instanceIp'


Once logged into the EC2 instance:
- to check GPU is setup correctly use the command : $ nvidia-smi
- to keep track of your history use the command : $ sudo rm .bash_history
- to check CUDA version : $ nvcc --version


To fix some cudann error message you may have to do this (see stackoverlfow):
- $ export LD_LIBRARY_PATH="/usr/local/cuda-8.0/lib64"
- $ export CUDA_HOME=/usr/local/cuda-8.0
- $ source ~/.profile


By default the Jupyter notebook password will be : dl_course

The latest version of Keras 1 (as of today)
$ pip install keras==1.2.2


Update .keras/keras.json to use tensorflow backend


$conda create -n py35_kr_tf python=3.5 anaconda
$ source activate py35_kr_tf
$ pip install --ignore-installed --upgrade https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.1.0-cp35-cp35m-linux_x86_64.whl
$ (conda install -c conda-forge keras=1.2.2) or (pip install keras==1.2.2)
$ source deactivate
