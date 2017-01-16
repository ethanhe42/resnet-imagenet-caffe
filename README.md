# train resnet imagenet with caffe
### resnet-18
### resnet-32
This is a bottleneck architecture,  
Since there's no strong data augmentation and 10-crop test in caffe, the results maybe a bit low.  
test accuracy: accuracy@1 = 0.67892, accuracy@5 = 0.88164  
training loss for resnet-32 is shown below:  
the pretrained model is provided [here]()
![a](resnet_32/loss.png)

