# ResNet on ImageNet with Caffe

[GitHub - yihui-he/resnet-imagenet-caffe: train resnet on imagenet from scratch with caffe](https://github.com/yihui-he/resnet-imagenet-caffe)

All models are trained on 4 GPUs with a minibatch size of 128. Testing is turned off during training due to memory limit(at least 12GB is require). The LMDB data is obtained from the [official caffe imagenet tutorial](http://caffe.berkeleyvision.org/gathered/examples/imagenet.html)

To train a network, use train.sh. For example, train resnet-50 with gpu 0,1,2,3:

```bash
#set caffe path in train.sh
mkdir resnet_50/logs
mkdir resnet_50/snapshot
./train.sh 0,1,2,3 resnet_50 resnet_50_
```

**For better training results, please install [my Caffe fork](https://github.com/yihui-he/caffe-pro), since the official Caffe ImageData layer doesn’t support original paper’s augmentation (resize shorter side to 256 then crop to 224x224). Use my 224x224 mean image `bgr.binaryproto` accordinglySee `resnet_50/ResNet-50-test.prototxt` ImageData layer for details**

### Citation

If you find the code useful in your research, please consider citing:

```
@InProceedings{He_2017_ICCV,
author = {He, Yihui and Zhang, Xiangyu and Sun, Jian},
title = {Channel Pruning for Accelerating Very Deep Neural Networks},
booktitle = {The IEEE International Conference on Computer Vision (ICCV)},
month = {Oct},
year = {2017}
}
```

### resnet-50

use `resnet_50/ResNet-50-test.prototxt` for training and validation

(new) We’ve release a [2X accelerated ResNet-50](https://github.com/yihui-he/channel-pruning/releases/tag/ResNet-50-2X) caffemodel using [channel-pruning](https://github.com/yihui-he/channel-pruning)

[](https://yihui-he.github.io/blog/channel-pruning-for-accelerating-very-deep-neural-networks)

### resnet-32 This is a bottleneck architecture,

Since there’s no strong data augmentation and 10-crop test in caffe, the results maybe a bit low.

test accuracy: accuracy@1 = 0.67892, accuracy@5 = 0.88164

training loss for resnet-32 is shown below:

the trained model is provided in [release](https://github.com/yihui-he/resnet-imagenet-caffe/releases/download/v1.0/resnet_32_iter_750000.caffemodel)

![https://raw.githubusercontent.com/yihui-he/resnet-imagenet-caffe/master/resnet_32/loss.png](https://raw.githubusercontent.com/yihui-he/resnet-imagenet-caffe/master/resnet_32/loss.png)

### Other models on Caffe

[](https://yihui-he.github.io/blog/resnet-on-cifar-10-with-caffe)

[](https://yihui-he.github.io/blog/xception-with-caffe)
