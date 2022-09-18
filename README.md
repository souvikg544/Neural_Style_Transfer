# Neural Style Transfer

As the name suggests Neural Style Transfer is a way of transfering the style of one image to the other image.
How? 
To explore our question of how , lets take a short learning journey --->

We will begin with understanding Vgg19

![vgg19](https://user-images.githubusercontent.com/63863911/190919611-2f980fce-8992-41b9-a324-b3b77c424e16.PNG)

But then Vgg19 is used for image classification right ? What is its role in style transfer ?

Before understanding it ...lets see the content image and the style image
![download (2)](https://user-images.githubusercontent.com/63863911/190920274-7c6d99a1-0127-474d-9052-75637a6162f2.png)


Lets suppose you pass an image though the Vgg19 network ... In the first layers namely conv128 or conv 256 in the image above the style of the image is kept almost intact. By style here we mean the background and overall frame . Whats more ! since it is a feature extractor visualizing these outputs gives an artistic feel too.Lets pass our style image below to these layers below --->

The last layer or the layers a bit before the last layer have completed extracing all the features of the image and are left with important features and edges of the image. This thus gives an outline of the image like the outline of the pers


Having found both the content and the style, we now have to find a way to superimpose them.
The process is a bit complicated. We compute the style loss from the style image and the content loss from the content image. We sum up this losses to calculate the total loss.We use an Adams optimizer to minimize the loss over given epochs. This final steps have a lot of complexity but can be summed up with these lines.One of them is how we calculate the losses using the Gram Matrix.. Lets keep that learning for a later part of the day and see our resulting image here --->


![dog3](https://user-images.githubusercontent.com/63863911/190920490-870c7024-dccb-49be-b930-d506fa09c415.png)


You can view the notebook above having the implementation . It is an official notebook by tensorflow . A better model trained on more epochs following the same logic can be accessed at Tensorflow Hub. 
Link - https://tfhub.dev/google/magenta/arbitrary-image-stylization-v1-256/2



