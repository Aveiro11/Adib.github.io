---
title: "Image Caption Generator"
collection: projects
permalink: /projects/project1
excerpt: ''
project url: 'https://github.com/Aveiro11/Image-caption-Generator'
---
In my approach, I used a CNN as the 'image model' and an RNN/LSTM as the 'language model' to encode text sequences of varying lengths. The vectors generated from both encodings were merged and processed by a Dense layer to make the final prediction.
![image](https://github.com/Aveiro11/Adib.github.io/assets/74791612/6c2193be-4166-4b4c-a800-25c1ed806ee1){: .align-right width="300px"}

I created a merge architecture to keep the image separate from the RNN/LSTM, allowing me to train the image-handling and language-handling parts of the neural network independently, using distinct training sets for images and sentences.

In my merge model, I combined a different representation of the image with the final RNN state before each prediction.The merging of image features with text encodings at a later stage in the architecture was advantageous and generated better quality captions with smaller layers than the traditional inject architecture (CNN as encoder and RNN as decoder).

To encode the image features, I used transfer learning. There are many models available for this purpose, such as VGG-16, InceptionV3, and ResNet. I chose the InceptionV3 model because it had the fewest training parameters compared to the others and also outperformed them.

To encode the text sequence, I mapped every word to a 200-dimensional vector using a pre-trained Glove model. This mapping was done in a separate layer after the input layer, called the embedding layer.

To generate the captions, I used two popular methods: Greedy Search and Beam Search. These methods helped in selecting the best words to accurately describe the image.

**Dataset used**: [Flickr 8k image dataset](https://www.kaggle.com/datasets/shadabhussain/flickr8k?select=train_encoded_images.p)
[Visit my Repo here](https://github.com/Aveiro11/Image-caption-Generator)
