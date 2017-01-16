# train resnet imagenet with caffe
All models are trained on 4 GPUs with a minibatch size of 32.
### resnet-18
coming soon
### resnet-50
coming soon
### resnet-32
This is a bottleneck architecture,  
Since there's no strong data augmentation and 10-crop test in caffe, the results maybe a bit low.  
test accuracy: accuracy@1 = 0.67892, accuracy@5 = 0.88164  
training loss for resnet-32 is shown below:  
the trained model is provided in [release](https://github.com/yihui-he/resnet-imagenet-caffe/releases/download/v1.0/resnet_32_iter_750000.caffemodel)
![a](resnet_32/loss.png)

