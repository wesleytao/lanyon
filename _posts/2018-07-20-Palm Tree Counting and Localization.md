# Palm Tree detection and Counting for High Resolution Satellite Images
## About
In agriculture, palm tree cultivation is one of the big sectors with a huge market value. Palm trees are used to produce a variety of products like vegetable oil, bio-fuel, papers, furniture, decorations,
fodder for cattle etc. It also has to be mentioned that palm oil is the most widely used vegetable oil in the world.  
It is necessary to plan well during cultivation and to monitor different aspects of trees like proper inventory, health, size, heights etc., at different stages of their life.  
As palm tree cultivation zones are huge and difficult to be monitored visually on ground, images analysis can play a vital role in delivering those data and analysis, cost and labor efficiently from
the satellite or aerial images.

## Project Objective
This project investigates on one aspect, more specifically **localizing and counting palm trees** for creating their inventory, as an initial step towards the multifaceted monitoring.

## Dataset and Processing
Train data set contains pixel-level label informatoin. This is done by professionals and achieved best human-eye accuracy.
All of these data are **the property of the company of Adatos and they are not included in this repository.**
* Stage 1
  * Train data set:  4 channel, resolution 1341*2048 , 4 mask has difference size.
    * orthogonal.tif
    * orthogonal_mask0.tif
    * orthogonal_mask1.tif
    * orthogonal_mask2.tif
    * orthogonal_mask3.tif

  * Test data set: we cut images into pieces and sample some images as test data.
  {# Test} / {# Train}  = 10-20%

* Stage 2
  * Train data set: 3 channel
    * KILE_sample.tif  (2560*2560)
    * KILE_sample_mask.tif (2560*2560)
  * Test data set:
    * gab_SIR_bawah.jpg (24051*15908)
    * KILE.tif (18500*16976)


## Methods
1. Blob Detection
The objective of blob detection is very simple, to detect circle shape in the image.
One benefit of this model is that it doesn't require label data and very cheap. However, there are two downsides of this method, tuning parameter need human eye check picture by picture. Another problem is computation expensive. If we would like to achieved better result.  Laplacian of Guassian Approach need more computation power.

There are 3 types of blob detection:
 * Simple Blob Detection  (no preprocess)
 * Laplacian of Guassian  Approach
 * Difference of Gaussian Approach
Also, there are many ways to do preprocess, by setting a strong contrast might help.

2. Convolution Neural Network
![myimg](/figs/Lnet.png)

3. Fully-Connected Neural Network

4. U-Net Image Segmentation


## Evaluation and Results
![origin](figs/stage1/stage1.png)
![label](figs/stage1/stage1_label.png)
![pred](figs/stage1/stage1_pred.png)

* metrics
  * accuracy:
  * IoU(Intercept over Union):     
  (table to show)

## Improvement and limitations

## Data pipeline and Automation


## Reference and Resources

This project is led by Chief Data Scientist Cui Han at Atados.ai https://www.adatos.com/product
