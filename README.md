# Anime Sketch Generator Based on GAN and CNN
We made a web application to generate sketch anime in the project. The website could receive the stick figure as input and then returns an anime sketch as the output. In the process of solving this problem, we explored the method to build GAN and CNN for anime generation. After our experiment, we achieved the goal to do anime generation. With more figures and better pose structure, this application will have better performance. 

# Data Collection
The collected Dataset contains two sets of pictures. They are labeled by ourselves. We regard the human body as a joint-stick system with 11 joints and 10 sticks. We labeled the figure with the joint position data, and the label of each figure is a 22 dimensions list.

The Sketch Dataset includes 500 300x300 pixels human pose sketch png images. It was collected from anime characters database. 

The 3D-model Dataset contains 1000 600x600 pixels human pose png images. These images are projections of 3d human model. The model is provided by Manga Editor. We created 1000 model pose and projected it to be the 3D-model images through thresholding and gaussian blur.

The Generated Dataset is the dataset whose data was mainly generated by our OpenCV generation program. It contains two different datasets. One is the stick figure dataset, and the other is the basic 3D-model dataset.


# CNN Model
In deep learning, a Convolutional Neural Network (CNN, or ConvNet) is a class of deep neural networks, most commonly applied to analyzing visual images. They have applications in image and video recognition, recommending systems, image classification, medical image analysis, and natural language processing.

We implemented two CNN models with the same structure. One is for stick figure recognition, and the other is applied for the output figure recognition. As the performance of GAN was not good enough. We tried to build a database based on the 3D-model dataset and used the CNN way to combine the input figure with the most suitable picture in the 3D-model dataset. 


# GAN Training
Generative Adversarial Network (GAN) shows impressive results in image generation, image transfer, super-resolution and many other generation tasks. GAN model trains a generator model and a discriminator model at same time, where the discriminator tries to distinguish the real example, sampled from ground-truth images, from the samples generated by the generator. On the other hand, the generator tries to produce realistic samples that the discriminator is unable to distinguish from the ground-truth samples.

An original generative adversarial network(GAN) contains two main parts, generator and discriminator. For the first part, a generator work as a neural network transmitting a white noise input picture to a fake picture similar to the real sample. Then, the fake pitcure will be sent to the discriminator with a real one as the training data as the second part, to let the discriminator judge which is the true sample. After the jedging process, the output should be compared with the real data and the loss function of discriminator and generator would be computed. Backpropagation is the final step to update the characters of these two networks. We choose Adam as the optimizer and BCEL as the loss function.

# Conclusion
In this project, we constructed a web-based application to recognize the input of a stick figure and return an output of a figure with similar pose from the dataset or generated from the GAN generator. In order to complete this application, we collected figure data from anime characters database and Manga Editor, and created a OpenCV-based figure generation. The application includes two system, one is a CNN to CNN method, and the other is the CNN to GAN method. The application is able to generate proper output, but the performance of it need to be improved.

In the future, in order to improve the performance of this application, more data should be collected and the structure of the GAN system should be improved to make a tighter connection between the pose data and the pose figure.
