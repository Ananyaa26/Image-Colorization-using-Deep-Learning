# Image-Colorization-using-Deep-Learning

***Image colorization*** is the process of assigning colors to a grayscale image to make
it more aesthetically appealing and perceptually meaningful.

Grayscale image colorization can be used for ***historical data restoration, old
photos colouring,coloring astronomy photographs*** etc., and make those products
contain additional visual information.

In this project, we propose a method for image colorization. We preprocess
colored images to create grayscale images to use as the input for the model. Our
model is then trained with these grayscale images as input and the original
colored images as the output.
So, if we feed a new unseen grayscale image to the model, it would be able to
generate an RGB image with a reasonable understanding of the spatial
relationship of color with the inherent texture.

# DataSet
The Natural-Color Dataset (NCD) is an image colorization dataset where images are true to their colors.
It contains 723 images from the internet distributed in 20 categories. Each image has an object
and a white background.

<img width="500" alt="image" src="https://user-images.githubusercontent.com/89255668/226542764-25408dbc-ab1f-431d-b37f-16dacbd55dcc.png">


# The Concept of RGB and LAB channels 

<img width="700" alt="image" src="https://user-images.githubusercontent.com/89255668/226543914-77f4fa5e-0b95-4ac6-8f11-7577b636a6ca.png">


# Implementation Approach
### 1) VGG-19 Architecture of deep CNN
### 2) AutoEncoders using transfer learning

<img width="750" alt="image" src="https://user-images.githubusercontent.com/89255668/226542865-73a1d980-40f5-4061-b76a-c204a11a3a4e.png">

An **autoencoder** is a neural network that is trained to attempt to copy its input to its output.They are an unsupervised learning method, although technically, they are trained using supervised learning methods, referred to as self-supervised.

**VGG** model has been borrowed as encoder.It has the lighting attribute of the images and no color information is there.It has been used for feature extraction.

The **decoder** predicts the 2 channels of colors for the image.

```
1)Convert all training images from the RGB color space to the LAB color space
2)Use the L channel as the input to the network and train the network to predict the ab chnnels
3)Combine the input L channel with the predicted ab channel
4)Convert the LAB image back to RGB.
```

<img width="445" alt="image" src="https://user-images.githubusercontent.com/89255668/226543137-d460f72f-c8b2-47a5-8f81-fbd40e5b0233.png">                                                                         <img width="505" alt="image" src="https://user-images.githubusercontent.com/89255668/226546997-4aefedf1-5d25-47ea-b2ab-807d997d99c7.png">

# Observations
There was a huge range in accuracy with slightest variation in number of
epochs.

<img width="600" alt="image" src="https://user-images.githubusercontent.com/89255668/226543366-8e07b8e2-ea2e-44c9-8b90-6c9b90e4e22d.png">

***The above graph shows the Loss and Accuracy curves with respect to the increase in Epochs.***

# Evaluation Metrics - Image Similarity Index
## RMSE (Root Mean Square Error)
It measures the amount of change per pixel due to the
processing. RMSE values are non-negative and a value of 00 means the image or videos
being compared are identical. The RMSE between a reference or original image, image1 -
Kimage1−K and the enhanced or predicted image, image2 - I(i, j)image2−I(i,j) is given by:

<img width="450" alt="image" src="https://user-images.githubusercontent.com/89255668/226543566-a9396b21-ac16-4dc3-bb11-13d5b5b3dc03.png">



## PSNR (Peak Signal to Noise Ratio) 
It measures the ratio between the maximum possible
power of a signal and the power of corrupting noise that affects the fidelity of its
representation. PSNR is usually expressed in terms of the logarithmic decibel scale.

<img width="300" alt="image" src="https://user-images.githubusercontent.com/89255668/226543639-0101fd13-1150-4e60-9718-7187ffd98ded.png">


## SSIM(Structural Similar Index Measure) 
It quantifies image quality
degradation caused by processing, such as data compression, or by losses in
data transmission. SSIM is based on visible structures in the image. In other
words SSIM actually measures the perceptual difference between two similar
images.

<img width="460" alt="image" src="https://user-images.githubusercontent.com/89255668/226543713-b24b98b9-c8a5-44f5-9470-84277f355677.png">




# Result

<img width="800" alt="image" src="https://user-images.githubusercontent.com/89255668/226549934-a8605b9d-3342-4f47-8717-ebb9cf1901d9.png">

# Resources
[Dataset](https://drive.google.com/drive/folders/1jt9uTysRLrzdsPsx6sNssujnDZzx57qB?usp=share_link)  

[dblp Paper](https://ietresearch.onlinelibrary.wiley.com/doi/10.1049/ipr2.12452)  

[IEEE Conference Paper](https://deepai.org/publication/image-colorization-a-survey-and-dataset)  

[Medium Article](https://emilwallner.medium.com/colorize-b-w-photos-with-a-100-line-neural-network-53d9b4449f8d)  

[CNN](algoritmaonline.com)  

[Autoencoder](https://youtu.be/bIaT2X5Hd5k)

[Reference Paper 1](https://arxiv.org/pdf/2008.10774.pdf)  

[Reference Paper 2](https://richzhang.github.io/colorization/resources/colorful_eccv2016.pdf) 

