---
title: Architectures neuronales pour la vision par ordinateur
keywords: IA, cvision
last_updated: March 09, 2025
tags: [IA, cvision]
summary: "Principales architectures neuronales pour l'analyse d'images"
sidebar: mydoc_sidebar
permalink: cvision_architectures.html
folder: mydoc
---

[https://d2l.ai/chapter_attention-mechanisms-and-transformers/vision-transformer.html](https://d2l.ai/chapter_attention-mechanisms-and-transformers/vision-transformer.html)

Article [*Comprehensive comparison between vision transformers and convolutional neural networks for face recognition tasks*](https://www.nature.com/articles/s41598-024-72254-w)

CNNs operate through a series of layers, each of which detects different features in an image by applying various filters, and sends them to the subsequent layer. These filters can initially begin detecting very simple features, and increase in complexity to detect features that uniquely identify a specific object or category.

ViTs break an image into patches, which are flattened and turned into a series of tokens through a linear projection to enable them to be fed into the network. These tokens are passed through a series of transformer encoder layers, which exhibit a remarkable capacity for understanding how different parts of the picture relate to each other. This is achieved by means of a multi-head self-attention mechanism. 

major differences 
1) large field of view of the initial ViTs’ layers
- CNNs employ a fixed-size kernel field of view, gradually extending it by repeatedly convolving the information around the kernel layer by layer -> need to propagate layers to obtain global representations
- ViTs utilize a self-attention mechanism that enables the model to have a whole field of view, even at the lowest layer -> global representations from the beginning ; require large amounts of data to obtain local representations in the lowest layers but can be addressed through a well-designed pre-training strategy.

2) memory footprint 
- CNNs : during training, must save all intermediate activation maps resulting from the performed convolutions ; can quickly restrict the maximum number of samples in a batch, which in turn can affect the ability of the model to converge
- ViTs : the initial step divides the image into tokens, which have a much smaller memory footprint than activation maps during training




1.	Architectures neuronales pour la vision par ordinateurs

Vision transformer
* [https://www.v7labs.com/blog/vision-transformer-guide](https://www.v7labs.com/blog/vision-transformer-guide)
* [https://viso.ai/deep-learning/vision-transformer-vit/](https://viso.ai/deep-learning/vision-transformer-vit/)
* [https://amaarora.github.io/posts/2021-01-18-ViT.html](https://amaarora.github.io/posts/2021-01-18-ViT.html)
* [https://tugot17.github.io/Vision-Transformer-Presentation](https://tugot17.github.io/Vision-Transformer-Presentation)
* [https://medium.com/@hansahettiarachchi/unveiling-vision-transformers-revolutionizing-computer-vision-beyond-convolution-c410110ef061](https://medium.com/@hansahettiarachchi/unveiling-vision-transformers-revolutionizing-computer-vision-beyond-convolution-c410110ef061)
* Article [AN IMAGE IS WORTH 16X16 WORDS](https://arxiv.org/pdf/2010.11929)


{% include links.html %}

