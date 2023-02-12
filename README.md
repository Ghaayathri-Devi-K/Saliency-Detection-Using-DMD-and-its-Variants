# Saliency-Detection-Using-DMD-and-its-Variants

<p style='text-align: justify;'> Visual saliency is the ability to differentiate the important parts of the image so that they stand out from their neighbors and grab our attention. It decreases the amount of visual data that is to be processed. It is very crucial, as images can be processed without knowing their actual contents. In this project, we have detected saliency regions of an image using dynamic mode decomposition (DMD) and its variants (rSVD-DMD, TDMD). A novel method of image representation was employed to make DMD applicable to static images. We have utilized color and luminance information and generated a saliency map. The complex and non-linear nature of the human visual system is modeled by making use of the power of the different color spaces to generate a color based saliency map. The fact that the sensitivity of the human eye towards brightness is higher than color is utilized to generate luminance saliency maps. The method employed is computationally less expensive, straightforward, and produces full-resolution saliency maps. The validity of the generated saliency map is estimated using standard performance measures such as F-measure, precision, recall, mean absolute error (MAE), and area under the ROC curve </p>  

**_Need for DMD:_**  

<p style='text-align: justify;'> The conventional methods take either the spatial components or the temporal components to generate saliency maps, while the DMD takes both the spatial and temporal components into account to generate saliency maps. It is computationally efficient and gives better results than the conventional methods. </p>

###  Objective
<p style='text-align: justify;'> The main objective of this project is to exploit the analytical power of DMD and its variants, such as randomized SVD DMD, total DMD, to generate saliency maps and to visually and quantitatively analyze the effectiveness of each of these variants. This project also aims to analyze color spaces in order to improve image representation by separating luminance and chrominance and generating the saliency map. Also, the spatial information of the generated saliency map is utilized to further enhance it. </p>  

### DMD
<p style='text-align: justify;'> The dynamic mode decomposition (DMD) is the foremost algorithm to decompose complex systems into spatiotemporal coherent structures, or modes. These are then used for short term future state prediction and control. Generally, dynamic mode decomposition identifies modes that are spatially correlated and oscillate at a fixed frequency in time with a growing or decaying envelope. As a result DMD is considered as an ideal combination of </p>  

1. Model reduction technique  
2. Fourier transforms in time  

<p style='text-align: justify;'> In this project, we investigate the efficacy of the DMD and its variants, such as the randomized singular value based DMD and the total DMD, for saliency region detection of an image.  </p>

![image](https://user-images.githubusercontent.com/120790343/218320215-21c77767-b5f3-408b-a6e6-54d17528e33c.png)

### RSVD - DMD  

<p style='text-align: justify;'> Singular value decomposition is a matrix factorization technique that computes the low rank matrix approximation of the data points. In order to obtain a faster and more efficient low rank 
approximation, randomization concepts are introduced. The rSVD factorization is done as follows: </p>  

1. For a given input matrix, a low dimensional subspace is constructed
2. Standard factorization is performed for the constructed basis by confining the input matrix to the low dimensional subspace.

![WhatsApp Image 2023-02-12 at 20 57 08](https://user-images.githubusercontent.com/120790343/218320590-24fc2a4d-8d11-4992-815a-63d1e205cd9e.jpg)

### Static Image Interpretation via DMD
<p style='text-align: justify;'>Here, an RGB image of size (mxn) is converted to different color spaces such as CIELab, YUV and YCbCr. With the different color space transformations, the images are better represented and have the capability of separating luminance and chrominance. The chrominance and the luminance are based on the degree of receptivity towards brightness and color information. </p>  

- Channels used to generate saliency map based on luminance
1. Y1 from YUV
2. Y2 from YCbCr
3. L from CIELab  

- Channels used to generate saliency map based on color
1. U and V from YUV
2. Cb and Cr from YCbCr
3. a and b from CIELab

### Colour Space Analysis
![image](https://user-images.githubusercontent.com/120790343/218321118-71a7c786-7b73-45df-b7da-52cc2c033ed3.png)
![image](https://user-images.githubusercontent.com/120790343/218321194-6d7a7dda-cd9e-4d42-b8a6-b752d7468bba.png)
![image](https://user-images.githubusercontent.com/120790343/218321209-7497b633-6a69-4723-a385-580563ad9b25.png)  
<p style='text-align: justify;'>We can see from this that salient regions in an image have varying degrees of apparentness in 
different color channels. The salient regions are more prominent in more than one color channel. 
From the above analysis, we observe that salient regions are clearer in b from CIELab, V from 
YUV and Cr from YCbCr channels for the image that have clear distinct differentiation between 
salient part and background. Similarly, the salient regions are clearer in a from CIELab, U from 
YUV and Cb from YCbCr channels for the image that have a blurred background </p>
   
### Luminance based DMD representation of images
![image](https://user-images.githubusercontent.com/120790343/218321277-48193252-42ea-4d3a-a51e-9ee6ed63c39e.png)

<p style='text-align: justify;'>We can observe that the SVD-reconstructed images have more salient features. Also, as the number of singular values used for reconstruction increases, the salient region becomes clearer while the background remains relatively static after a set of iterations. </p>
    
### Salient region detection using dynamic mode decomposition  


#### Color based saliency map
![image](https://user-images.githubusercontent.com/120790343/218321545-6f95e6d7-c376-4fba-bb09-b83fb11bfd97.png)
<br>
<br>
#### Luminance based saliency map
![image](https://user-images.githubusercontent.com/120790343/218321640-3de8f0e3-ccd9-4a71-9b3c-750c9358a529.png)
<br>
<br>
### Qualitative Analysis
![image](https://user-images.githubusercontent.com/120790343/218321753-1bec54c4-2059-4fbc-a235-b5a9b9a71aee.png)
![image](https://user-images.githubusercontent.com/120790343/218321765-1c9eef43-419b-4f0f-bb1e-5dc45b5f8f87.png)  

### Datasets
<p style='text-align: justify;'> In this project, we have used the ECSSD (Extended Complex Scene Saliency Dataset). It consists of 1000 images, which includes many semantically meaningful and structurally complex images for evaluation. The images that fall into the category of natural images are present here. These images have textures and structures common to real world images. Several examples with their masks are provided. We used 100 random images from this dataset for quantitative comparison.</p>  

**_Link For Dataset:_** [Click here](https://www.cse.cuhk.edu.hk/leojia/projects/hsaliency/dataset.html)  

![image](https://user-images.githubusercontent.com/120790343/218324321-a9175183-3145-410d-961a-f1f0e7d0857b.png)



### Quantitative Analysis
#### Precision - recall [PR]
![image](https://user-images.githubusercontent.com/120790343/218322006-8beec0e7-142e-41dc-a833-6cf0c70aa635.png)
<br>
<br>
#### F-measure
![image](https://user-images.githubusercontent.com/120790343/218322159-cd3fc7af-e7d4-47c5-b960-9d1ea289b600.png)
<br>
<br>
#### Mean absolute error
![image](https://user-images.githubusercontent.com/120790343/218322189-47328b8e-22ab-479c-8df7-09fc4f8cab84.png)
#### Area under ROC curve
**_Standard DMD:_**  

![image](https://user-images.githubusercontent.com/120790343/218322842-fd1c90c3-143e-419f-8762-23f6e7f1e552.png)
<br>
<br>
**_rSVD-DMD:_**  

![image](https://user-images.githubusercontent.com/120790343/218322886-6cd5d882-0176-4bc2-a593-86da2e692961.png)


### Failure cases:
<p style='text-align: justify;'> The proposed method in this project is especially targeted for the natural scenes. It widely uses the general information of the images and is suboptimal for the images with highly textures background having the same color distribution as foreground. This method fails when the images have a highly structured background with the same color distributions as the foreground. The dynamic mode decomposition method captures the difference between consecutive columns in the data matrix and the modes bounded away from the origin are detected as the salient region. In scenarios where the background and foreground distributions in the image are highly overlapping and the background is highly textured, the color and intensity-based image representations become undesirable for the application of DMD.</p>  

### Conclusion  
From the experiments performed we can conclude that standard DMD offers satisfactory performance. The worst performance is obtained for rSVD-DMD because it is affected by the fluctuations and uncertainties in the measured data.
