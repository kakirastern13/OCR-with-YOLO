# Darknet for Veztan

The following are some instructions for setting up darknet for YOLOv3 in the AWS EC2 environment for the Veztan OCR project.
This project involves using deep learning (DL) to carry out first text detection, then text recognition, then to use the results
obtained from these to perform form identification task. 

To set up darknet for the OCR, please follow the steps below to first install `opencv`:
1. At the AWS command prompt, after doing `source activate <desired_evn>`, use conda to install opencv4: $ conda install -c conda-forge opencv
2. Then say for the conda env `pytorch_p36`: $ export PKG_CONFIG_PATH="/home/ec2-user/anaconda3/envs/pytorch_p36/lib/pkgconfig"
3. Afterwards, do: $ pkg-config --cflags opencv
