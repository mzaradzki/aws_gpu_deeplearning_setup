# aws_gpu_deeplearning_setup

YouTube tutorial from Jeremy Howard :

https://www.youtube.com/watch?v=8rjRfW4JM2I

The setup_instance.sh script assumes your .pem file name follows "aws-key-$name.pem" with $name being defined at the top.

If your .pem file name is "aws-key-fast-ai.pem" you can keep the aws-alias.sh file as it is but otherwise the following line needs to be modified :
alias aws-ssh='ssh -i ~/.ssh/aws-key-fast-ai.pem ubuntu@$instanceIp'


Once logged into the EC2 instance:
- to check GPU is setup correctly use the command : $ nvidia-smi
- to keep track of your history use the command : $ sudo rm .bash_history
