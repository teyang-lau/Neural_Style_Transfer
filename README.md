# **Neural Style Transfer for Artistic Style Pictures**

[![made-with-kaggle](https://img.shields.io/badge/Made%20with-Kaggle-lightblue.svg)](https://www.kaggle.com/)
[![made-with-python](https://img.shields.io/badge/Made%20with-Python-blue.svg)](https://www.python.org/)
[![made-with-Markdown](https://img.shields.io/badge/Made%20with-Markdown-1f425f.svg)](http://commonmark.org)
[![Generic badge](https://img.shields.io/badge/STATUS-COMPLETED-<COLOR>.svg)](https://shields.io/)
[![GitHub license](https://img.shields.io/github/license/teyang-lau/Dog_Breeds_Classification_CNN.svg)](https://github.com/teyang-lau/Dog_Breeds_Classification_CNN/blob/master/LICENSE)

Author: TeYang, Lau <br>
Last Updated: 9 August 2020

<img src = './Pictures/NST.jpg'>

### **Please refer to this [notebook](https://www.kaggle.com/teyang/neural-style-transfer-for-unique-artistic-photos) on Kaggle for a more detailed description, analysis and insights of the project.** 



## **Project Motivation** 

For this project, I applied deep learning and convolutional neural networks onto some of my own personal pictures, after finishing the [Convolutional Neural Network](https://www.coursera.org/learn/convolutional-neural-networks) course on Coursera by [Deeplearning.ai](https://www.deeplearning.ai/). This is more of a fun project to create  new artistic style pictures from my own pictures while at the same time brush up on my deep learning and CNN skills.



## **Project Goals** 

1. To create new artistic style photos by merging my own photos with a style photo
2. Understand the ways CNN can be modified for other purposes
3. Understand the core of how neural style transfer works 



## **Project Overview** 

* **Image preprocessing** for input into model
* Selecting **content and style layers** from CNN model
* Defining **generated, content and style cost** function
* **Minimizing the loss** between generated, and content and style images



## **About Neural Style Transfer** 

**Neural Style Transfer (NST)** is a machine learning optimization technique that uses 2 images - ***a content image*** and a ***style image***, and blends them together so the output (***generated image***) looks like the content image, but 'painted' in the style of the style image. This algorithm was first introduced by Gatys et al. in the paper called [A Neural Algorithm of Artistic Style](https://arxiv.org/pdf/1508.06576.pdf). The core innovation of NST is the use of deep learning to minimize the generated image's content and style so that it matches that of the content and style images. By doing so, it allows us to compose our own pictures in the style of any other paintings/pictures ranging from google images to famous paintings.

<img src = 'https://media.giphy.com/media/UqY2VYZY3u88vikIo6/giphy.gif' width="900">



## Content and Style Images

Here we will attempt to paint the content image in the style of the style image.

<img src = './Pictures/contentstyle.png'>



## Cost Function 

The cost function is the most important idea in neural style transfer. The overall idea is simple. We want the generated image to have the same content as the content image while having the same style as the style image. Therefore, we are looking to reduce the cost/loss of the generated image, which we define as the sum of its content cost and style cost:

<img src = './Pictures/totalcost.png'>



**Content cost** is defined as the euclidean distance between the activations of the content and generated image at a specific layer:

<img src = './Pictures/contentcost.png'>

**Style cost** is defined as the Frobenius norm of the gram matrices of the style and generated image at a specific layer:

<img src = './Pictures/stylecost.png'>



## **Generated Image** 

With each epoch in training the model, the generated image becomes more similar in content and style to the content and style images respectively. Refer to the [notebook](https://www.kaggle.com/teyang/neural-style-transfer-for-unique-artistic-photos) on Kaggle to look at this animated process! 

<img src = './Pictures/rainbow_face.png'>

<img src = './Pictures/mp_vg.png'>



## **Conclusions** 

Neural style transfer is a fun activity for learning deep learning and neural networks and can be a good way to take a break from doing/learning too much deep learning while still learning and practicing it. Fun aside, NST also has real life applications. For example, it can be used as a data augmentation tool for creating new medical images, especially for positive cases, which are usually more scarce compared to negative cases. It has also been used to improve [3D Cardiovascular MR Image Segmentation](https://arxiv.org/abs/1909.09716#:~:text=Recent%20years%2C%20deep%20neural%20networks,in%20medical%20image%20segmentation%20problem.&text=Specifically%2C%20neural%20style%20transfer%20algorithm,%2C%20contrast%2C%20texture%2C%20etc.). This is the era of deep learning and AI and I look forward to seeing what they can do and contribute to the medical and health industry.

