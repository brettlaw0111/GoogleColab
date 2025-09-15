# CNN (Convolutional Neural Network)
A CNN's main purpose is to work with images. 

Of course, its training data comes in the form of sets of images. 

Much like more basic neural networks, these have hidden layers of neurons. In a CNN, however, they also have a variety of **feature maps** and **convolutional layers**, which all play a part in analyzing images. 

## How does it analyze images? (More specifically determine the background)
When using a CNN, we represent the input images as an array. 

When inputting images with a clear background (i.e. white pixels), the value in the array is typically 0. 

If the image is in black and white, the black pixels are represented as 1. However, if it's a shade of gray, it's represented as a decimal between 0 and 1, the shade of gray being darker the closer it is to 1. 

By comparing the values in the array, the CNN can easily tell where the borders of the image are and where the background is. 

## What is an image filter / kernel?
Image kernels are a feature of CNNs that is used to extract important data from an image, such as edges, textures and patterns. 

They're small matrices, a 3x3 grid for example. The values of kernels are learned and determined by the CNN during the training process, and the values are updated using backpropagation to detect the important bits of an image. 

They stride over the image in a process called **convolution** and perform element-wise multiplication over the image array. By summing the results, important features like edges, corners and textures are extracted. 

In addition to length and width, kernels can have depth too. If an input image has RGB color channels, the kernel will have a depth of 3, one for each color channel. Each channel becomes another filter layer. 

An output of a kernel is a **feature map**. This shows specific features that were detected in the input image. Each kernel uses a different filter to detect a certain feature, so one may produce a feature map that highlights the edges in an image. 

Image kernels are the main component of convolutional layers.

## What is a convolutional layer?
Convolutional layers are the main building blocks of a CNN. They each have a  image filter / kernel of a certain type, which each extracts a specific feature of an image. They also have a set **stride size**, as well as **padding**, which is the process of adding extra pixels around an image to preserve its spatial dimensions during convolution.

Unlike the hidden layers in an ANN, the neurons in a convolutional layer aren't fully connected with one another. Rather, they're **locally connected** with a small amount of neurons. This is necessary since images can be very large, and a standard ANN would take too much processing power and probably blow up your computer. 

Once the feature map is created by the layer's kernel, it's typically fed into a pooling layer.

After running the input through all the convolution and pooling layers, the final stage is to run it through fully connected hidden layers, similar to those found in standard ANNs. 

## What is a pooling layer?
Pooling layers take the outputs from the convolutional layer and pools / reduces them.

Like the convolutional layers, the purpose of pooling layers is to save on computational resources. A pooling layer accomplishes this by reducing the amount of parameters. This process is called **downsampling** or **subsampling**. This process removes some data from the output of the convolutional layer(s), but if done well, keeps the trends in the data.

Pooling can be done with different methods, such as **max pooling**, where the maximum value of a section of data is selected, and **average pooling**, where the average of the section is taken.

Convolutional layers and pooling layers don't have to be in a set pattern. You could, for instance, have several convolutional layers before a pooling layer.

