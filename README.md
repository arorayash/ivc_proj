IMAGE VISION AND COMPUTING

# Multichannel Decoded Local Binary Patterns for Content Based Image Retrieval 

###
[Related paper](http://ieeexplore.ieee.org/document/7486086/?reload=true)

### Project brief
Local binary patterns (LBP) is a type of visual descriptor used for classification in computer vision. LBP is the particular case of the Texture Spectrum model. To describe the color images, it is required to combine the LBPs from each channel of the image. In traditional approach the LBPs of each channel are calculated and concatenated. However, this increase the dimensionality of the pattern. In order to cope with this problem, a novel method for image description with multichannel decoded local binary patterns is proposed. Adder and decoder based two schemas for the combination of the LBPs from more than one channel are introduced.
				
### Tech

* [Java](http://www.oracle.com/technetwork/java/javase/overview/java8-2100321.html) -  as core programming language
* [IntelliJ IDEA Editor](https://www.jetbrains.com/idea/) - IDE for JAVA development
* [OpenCV lib](http://docs.opencv.org/2.4/doc/tutorials/introduction/desktop_java/java_dev_intro.html) - an open source computer vision and machine learning software library.


### Introduction

To describe the color images using local patterns, several researchers adopted the multichannel feature extraction approaches. These techniques can be classified in four categories - 
 
![alt text](https://www.dropbox.com/s/0ltagb2vz187dr7/image18.png?dl=1){:width="50%"}

Here, two multichannel decoded local binary pattern approaches namely multichannel adder based local binary pattern (𝑚𝑎𝐿𝐵𝑃) and multichannel decoder based local binary pattern (𝑚𝑑𝐿𝐵𝑃) to utilize the local binary pattern information of multiple channels in efficient manners. Total 𝑐 + 1 and 2𝑐 number of output channels are generated by using multichannel adder and decoder respectively from 𝑐 number of input channels for 𝑐 ≥ 2. 


### Description and Approach

Consider the given input image - 

![alt text](https://www.dropbox.com/s/sgaw1w2h5mj8ac2/image6.jpg?dl=1)

The image is first split into three (Red, Green, Blue) channels.
    
![alt text](https://www.dropbox.com/s/w4cgblsz8hka20r/image1.jpg?dl=1)      ![alt text](https://www.dropbox.com/s/dis7wnf9lioapp2/image14.jpg?dl=1)       ![alt text](https://www.dropbox.com/s/714u9yls34gm111/image23.jpg?dl=1)

Each channel is then padded in order to calculate the Local Binary Pattern. The procedure for calculating LBP is given as follows -

![](https://www.dropbox.com/s/moebl416rpo36z1/image9.png?dl=1)
 

- Divide the examined window into cells.
- For each pixel in a cell, compare the pixel to each of its 8 neighbors (on its left-top, left-middle, left-bottom, right-top, etc.). Follow the pixels along a circle, i.e. clockwise or counterclockwise.
- Where the center pixel's value is greater than the neighbor's value, write "0". Otherwise, write "1". This gives an 8-digit binary number (which is usually converted to decimal for convenience).
- Compute the histogram, over the cell, of the frequency of each "number" occurring (i.e., each combination of which pixels are smaller and which are greater than the center). This histogram can be seen as a 256-dimensional feature vector.
- Concatenate histograms of all cells. This gives a feature vector for the entire window.

For simplicity, we consider 8 neighbours and radius of 1 unit.

![](https://www.dropbox.com/s/jspfupgezsk6eqv/image8.png?dl=1)

### The formulae for calculating the LBP of a channel are given as  -

![](https://www.dropbox.com/s/lynsmn0dqxykuv4/image22.png?dl=1)

While calculating the LBP for each channel, multichannel adder and decoder maps are used to calculate the maMn(x, y) and mdMn(x, y) values. The table is given as follows.

![](https://www.dropbox.com/s/1qoik5e9fgfrpsg/image24.png?dl=1)


![](https://www.dropbox.com/s/lb2u1dsftsq3opi/image10.png?dl=1)



		 	 	 		
The following formulae are used to calculate the Multichannel adder based local binary pattern for each input channels. The corresponding output are given.


![](https://www.dropbox.com/s/eba17e8v05lgd7r/image5.png?dl=1)

![](https://www.dropbox.com/s/bkidmvzaqd8uclj/image19.jpg?dl=1) ![](https://www.dropbox.com/s/nrtpl3frrym79c4/image20.jpg?dl=1)
![](https://www.dropbox.com/s/2fztul5irt3qdlm/image15.jpg?dl=1) ![](https://www.dropbox.com/s/zzwkmaitnkf8aaj/image7.jpg?dl=1)


The following formulae are used to calculate the Multichannel decoder based local binary pattern for each input channels. The corresponding output are given.


![](https://www.dropbox.com/s/vqd28gh1gcff2bp/image21.png?dl=1)

![](https://www.dropbox.com/s/l9140askcojm8tg/image26.jpg?dl=1) ![](https://www.dropbox.com/s/la92b3bce6zxqwl/image17.jpg?dl=1) ![](https://www.dropbox.com/s/0kixazdwk3iz35a/image4.jpg?dl=1) ![](https://www.dropbox.com/s/ibxzhqpnw4fkfqq/image2.jpg?dl=1) ![](https://www.dropbox.com/s/qofutgf0dmw11a3/image3.jpg?dl=1) ![](https://www.dropbox.com/s/uwgpjz00egt34a7/image13.jpg?dl=1) ![](https://www.dropbox.com/s/kxp0jorckmb8s1n/image25.jpg?dl=1) ![](https://www.dropbox.com/s/wmlrkbrhxbkfk4p/image16.jpg?dl=1)

The feature vectors are then calculated using the following formulae - 

![](https://www.dropbox.com/s/dc9vnnumy1xga5c/image11.png?dl=1)



### Inference and conclusion
			
It can be perceived that the decoder channels are having a better texture differentiation as compared to the adder channels and input channels while adder channels are better differentiated than input channels. In other words, we can say that by applying the adder and decoder transformation the inter channel de-correlated information among the adder and decoder channels increases as compared to the same among the input channels. Four and eight output channels are produced by the adder and decoder respectively 
The calculated feature vector is used to define the image in the database and hence can be used to retrieve similar images based upon the image content.

![](https://www.dropbox.com/s/7nfg2p4ytxqci8r/image12.png?dl=1)

###
###
###
