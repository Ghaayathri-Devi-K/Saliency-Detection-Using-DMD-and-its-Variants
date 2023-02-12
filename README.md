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

