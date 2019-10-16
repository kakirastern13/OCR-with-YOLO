# Darknet for Veztan
The following are some instructions for setting up darknet for YOLOv3 in the AWS EC2 environment for the Veztan OCR project.
This project involves using deep learning (DL) to carry out first text detection, then text recognition, then to use the results
obtained from these to perform form identification task. 

To set up darknet for the OCR, please follow the steps below to first install `opencv`:
1. At the AWS command prompt (represented here with the symbol $), after doing `source activate <desired_evn>`, use conda to install opencv4: $ conda install -c conda-forge opencv
2. Then say for the conda env `pytorch_p36`: $ export PKG_CONFIG_PATH="/home/ec2-user/anaconda3/envs/pytorch_p36/lib/pkgconfig"
3. Afterwards, do: $ pkg-config --cflags opencv4

And after that, to make sure some darknet start problems will not arise due to some lib sharing issues, do: 
1. For the env `pytorch_p36` : $ sudo /bin/bash -c 'echo "/home/ec2-user/anaconda3/envs/pytorch_p36/lib" > /etc/ld.so.conf.d/opencv.conf'
2. $ sudo ldconfig

After which you may start using darknet...

## Downloading the weights required
There are two important weights files we will need to download in order to train the YOLOv3 CNNs. To download then to your 
EC2 instances, do the following at the command prompt ($): 
1. $ wget https://pjreddie.com/media/files/yolov3.weights 
2. $ wget https://pjreddie.com/media/files/darknet53.conv.74

To run darknet, do: 
$ nohup ./darknet detector train data/obj.data cfg/yolov3-veztan.cfg yolov3.weights -clear 1
Or: 
$ nohup ./darknet detector train data/obj.data cfg/yolov3-veztan.cfg darknet53.conv.74 -clear 1
