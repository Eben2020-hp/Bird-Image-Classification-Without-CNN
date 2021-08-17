# Bird-Image-Classification

## Dataset Description

The dataset consists of colored images of different birds divided into nine classes. The images are of different sizes and dimensions and are of .jpg format. 
Every image has a different orientation of the bird which adds sufficient amount of variability in the dataset and makes the classification model more robust. 

Number of records for each bird are as follows:

| Type of bird | Number of records |
| --- | --- |
| Baltimore Oriole	(Class 0) | 138 |
| Cockatoos (Class 1) | 166 |
| Cotinga (Class 2)	| 124 |
| Crow	(Class 3) | 107 |
| Macaw (Class 4) | 105 |
| Northern Cardinal (Class 5)	| 101 |
| Parakeets	(Class 6) | 135 |
| Parrot (Class 7) | 74 |
| Toucans (Class 8)	| 136 |


## Spatial based Feature Extraction

The MATLAB code uses various predefined functions to obtain spatial domain-based features. imresize( ) resizes each image to 400 x 400 pixels.
mean( ) , median( ) and std2( ) are used to obtain mean, median, and standard deviation of the pixel values, rgb2gray( ) converts colored image to gray scale image. 
The max( ) gives maximum of the pixel values, min( ) gives minimum of the pixel values and 
entropy( ) gives entropy of the image.


## Frequency based Feature Extraction

First the image is converted to a Red Channel image and stored in a structure.


Fast Fourrier Transformation is applied to the gray scale image using fft2().
We compute mean, median, maximum, and minimum of the pixel values of the transformed image using mean( ), median( ), max( ), and min( ).

#### Applying Discrete Cosine Transformation (DCT)

Coefficients are taken as features after applying DCT.

#### Applying Haar Wavelet Transformation ( 3 levels ) and computing statistical measures.

Mean, median, maximum and minimum of pixel values are computed after applying Haar wavelet transformation.

- **Storing the extracted features to a csv file using writematrix( ).**

## Normalization and Train-Test Split

Features may have very different ranges and hence feature values are normalized using MinMax scaler in Python 3.0.
Applying train test split to the data. ( 70% train and 30% test)

## Feature Description

| Feature | Description |
| --- | --- |
| RedMean	| Mean of the pixel values for Red channel |
| RedMedian	| Median of the pixel values for Red channel |
| GreenMean	| Mean of the pixel values for Green channel |
| GreenMedian	| Median of the pixel values for Green channel |
| BlueMean	| Mean of the pixel values for Blue channel |
| BlueMedian	| Median of the pixel values for Blue channel |
| Mean | Mean of the pixel values for gray scale image |
| Median | Median of the pixel values for gray scale image |
| Maximum | Maximum of the pixel values for gray scale image |
| Minimum | Minimum of the pixel values for gray scale image |
| Std_Dev	| Standard deviation for gray scale image |
| Skewness | Skewness of the pixel values for gray scale image |
| Kurtosis | Kurtosis of the pixel values for gray scale image |
| IQR	| Inter Quartile Range for gray scale image |
| Entropy	| Entropy of the pixel values for gray scale image |
| FFT_Mean | Average of the pixel values after applying Fast Fourrier Transformation |
| FFT_Median |	Median of the pixel values after applying Fast Fourrier Transformation |
| FFT_Maximum |	Maximum pixel value after applying Fast Fourrier Transformation |
| FFT_Minimum |	Minimum of the pixel values after applying Fast Fourrier Transformation |
| Wave_Mean	| Average of the pixel values after applying Haar Wavelet Transformation |
| Wave_Median	| Median of the pixel values after applying Haar Wavelet Transformation |
| Wave_Maximum	| Maximum of the pixel values after applying Haar Wavelet Transformation |
| Wave_Minimum | Minimum of the pixel values after applying Haar Wavelet Transformation |
| DCT	| Discrete Cosine Transformation of the image |
| Class | Class label |

## Classification

This is a multi-class classification problem with 9 classes.
