# Image-Super-Resolution
The goal of this project was to compare older, simpler convolutional neural network models to newer, more competitive transformer models on the problem of super-resolution. Using the Efficient Sub-pixel Convolutional Network for Super-resolution as our CNN and the Hybrid Attention Transformer as our transformer model, the team trained each network on the Flickr Faces High-Quality image dataset. It is shown that the transformer model generally outperforms the CNN on measurable factors such as peak signal-to-noise ratio. However, the subjective quality of the images produced by each network is similar. Further, training the convolutional network from scratch took under 6 hours and utilized around 35% of the total dataset, while doing the same for the HAT model took 8 hours and utilized only 10 images.

The architecture is similar to ESPCN paper, with only multiple additional convolution layers. 
The "depth_to_space” is used which enables the non-linear mapping from LR-space to HR-space. 
Also ESPCN paper uses greyscale so it is changed to be used color channels, not just greyscale.


![image](https://github.com/ipekmelisturk/Image-Super-Resolution/assets/91199985/d829ef77-9d2b-4ad9-b291-3ee79d46308a)


The HAT model is implemented in the local Pytorch. The biggest challenges we faced were due to hardware constraints since HAT works with 8 GPUs yet we only had 1. So various implementations have been tested to reduce computational complexity without compromising the model. 
The model implementation enables you to change the path, dataset, parameter, depth, optimizer, total iteration. The challenge was to start the code training. The model is firstly fine-tuned pre-trained model that uses ImageNet dataset and then it is trained using only FFHQ dataset.

![image](https://github.com/ipekmelisturk/Image-Super-Resolution/assets/91199985/04901bea-e3ae-4711-a88e-62d50a5fd550)

![image](https://github.com/ipekmelisturk/Image-Super-Resolution/assets/91199985/fde0a4c5-c3e8-469d-9c74-6f868ab3c87b)
