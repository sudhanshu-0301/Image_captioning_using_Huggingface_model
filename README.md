# Image_captioning_using_Huggingface_model

ViT and GPT2 are used to generate Image Caption for the uploaded image. Hosted on Huggingface - https://huggingface.co/spaces/Sudhanshu0319/Image_captioning


## Introduction

Image captioning is the process of generating caption i.e. description from input image. It requires both Natural language processing as well as computer vision to generate the caption.


## Concepts

### Vision Encoder Decoder Architecture
![model](https://github.com/sudhanshu-0301/Image_captioning_using_Huggingface_model/assets/103502520/6fb3f185-0405-4e79-8591-6333aeeb2fe2)

The Vision Encoder Decoder Model can be used to initialize an image-to-text model with any pre-trained Transformer-based vision model as the encoder (e.g. ViT, BEiT, DeiT, Swin) and any pre-trained language model as the decoder (e.g. RoBERTa, GPT2, BERT, DistilBERT). Here, we have used ViT as encoder and gpt2 as decoder.
Image captioning is an example, in which the encoder model is used to encode the image, after which an autoregressive language model i.e. the decoder model generates the caption.

* Encoder-Decoder architecture. Typically, a model that generates sequences will use an Encoder to encode the input into a fixed form and a Decoder to decode it, word by word, into a sequence.

* Attention. The use of Attention networks is widespread in deep learning, and with good reason. This is a way for a model to choose only those parts of the encoding that it thinks is relevant to the task at hand. The same mechanism you see employed here can be used in any model where the Encoder's output has multiple points in space or time. In image captioning, you consider some pixels more important than others. In sequence to sequence tasks like machine translation, you consider some words more important than others.

* Transfer Learning. This is when you borrow from an existing model by using parts of it in a new model. This is almost always better than training a new model from scratch (i.e., knowing nothing). As you will see, you can always fine-tune this second-hand knowledge to the specific task at hand. Using pretrained word embeddings is a dumb but valid example. For our image captioning problem, we will use a pretrained Encoder, and then fine-tune it as needed.

* Beam Search. This is where you don't let your Decoder be lazy and simply choose the words with the best score at each decode-step. Beam Search is useful for any language modeling problem because it finds the most optimal sequence.
![model](https://github.com/sudhanshu-0301/Image_captioning_using_Huggingface_model/assets/103502520/e8db94a4-5050-46c8-9e48-7cbb2569f2db)
