# Next Frame Prediction Paper Review

## Deep Learning in Next-Frame Prediction: A Benchmark Review

Paper:
https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=9063513

### Next-Frame Prediction
- unsupervised learning
- input : previous few frames 
- output : subsequent frames

A recurrent neural
network is rarely used in the sequence-to-one architecture,
while it is widely used in the sequence-to-sequence architecture.


For the loss function, L1, L2, and adversarial
loss are used in both architectures. Among them, the most frequently
used loss function is L2.


Here, they define a prediction system as a long-term prediction with 20 + frames. 

### **Sequence to One**

The input of the deep learning model is a set of frames in
time-step order between t and t+k. The prediction is the next
frame.
- pyramid of autoencoder model and GAN
- The generator is the autoencoder model where the

Autoencoder model consists of convolutional networks and the decoder consists of deconvolutional networks. The discriminator is a two-class classifier, which distinguishes the image generated by the generator from real data. The previous frames are resized into different sizes and fed into the overall network, while the output is the next frame with different scales.

**Github Repo for Models**
1. [CNN Autoencoder](https://github.com/tfxue/visual-dynamics)
    - immediate next frame with 1 frame input
2. [Pyramid of CNN + GAN](https://github.com/coupriec/VideoPredictionICLR2016)
    - feed in 4,8 frames and predic 1, 8 frames afterwards


### **Sequence to Sequence**
The input is temporal frames that are separately fed into the neural network. Specifically, the frame in time step t is input to the deep learning model, and the prediction is the next frame in time step t + 1.
- better captures the temporal information by incorporating RNN
- need to set different weights to each time point
- can combine autoencoder model or GAN with RNN to capture both spatial and temporal information

 The general sequence to sequence prediction model has the prediction model, which is composed of a recurrent neural network
and an autoencoder. The frame sequence is fed into the RNN. The total loss is composed of the difference
between the predicted images and the ground truth in each time step.


#### ConvLSTM 

**Github Repo for Model**
- [CNN autoencoder + LSTM](https://github.com/junhyukoh/nips2015-action-conditional-video-prediction)
    - input: 4, 11 frames | output: 1 frame | uses L1 loss


## Resources
