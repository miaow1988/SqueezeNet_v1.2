SqueezeNet v1.2
======================
Top-1 Acc=61.0% on ImageNet, without any sacrificing compared with SqueezeNet v1.1.

We improved SqueezeNet by the linear kernel compression idea, and got **61.0%** top-1 accuracy on ImageNet. 

In the original paper, each Fire model, which is the fundamental building block of SqueezeNet, consists of a squeeze part (a 1x1 convolutional layer with few filters) and a expend part (a 1x1 convolutional layer concatenated with a 3x3 convolutional layer, both of them have more filters compared with the squeeze part). 

We removed the RELU after the squeeze layer in each Fire model. Now the Fire model can be seen as a new model consists of the expand part only, and both layers in the expand parts are linearly compressed by a same 1x1 convolutional layer. 

In this way, we achieved 3% top-1 accuracy improvement on ImageNet based on SqueezeNet v1.1, without sacrificing parameter numbers and efficiency.

Implementation Details
======================
The network was trained by MxNet. Image size is 224x224, and the pixel mean for preprocessing is mean_r=124, mean_g=117,         mean_b=104. All other hyper parameters are as same as hyper parameters used in original SqueezeNet v1.1.