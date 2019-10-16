# cfg

Short for "config", this folder is - as its name suggests - intended for storing configuration files to be used to configure the darknet model
to train, test, or validate the dataset(s) concerned. 

For the current project, the file `yolov3-veztan.cfg` has been configured according to https://github.com/AlexeyAB/darknet#how-to-train-to-detect-your-custom-objects. 

Remember to use the following to ensure the out-of-memory (OOM) error will not come up during training:
* batch_size = 16
* subdivisions = 16
