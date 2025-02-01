<body>
<h1># DCGAN</h1>

This repository focuses on training a Deep Convolutional Generative Adversarial Network (DCGAN) on a dataset of butterfly images. <br>
The goal is to generate realistic butterfly images. Additionally, differentiable augmentations were applied during <br>                      training to improve the model's performance. The quality of the generated images was evaluated using the  <br>                               Fréchet Inception Distance (FID) metric.<br>
<pre>
<b><h3>Dataset</h3></b> <br>
The dataset consists of high-quality butterfly images. The images were preprocessed to ensure consistency in size and format. <br>
the dataset was taken from kaggle and can be found <a href = "https://www.kaggle.com/datasets/phucthaiv02/butterfly-image-classification/data">here</a><br>
</pre>
<pre>
  <h3><b>Architecture</b></h3>
The DCGAN consists of two main components: the Generator and the Discriminator.
<b>Generator</b>
Two architectures were experimented with:
Transpose Convolutions:
Uses transposed convolutional layers to upsample the latent vector into an image.
Upsampling with Convolutions:
Uses a combination of upsampling layers (e.g., bilinear or nearest-neighbor) followed by convolutional layers. This approach yielded better results.
<b>Discriminator</b>
A standard convolutional neural network (CNN) was used to classify images as real or fake.
Leaky ReLU activations and dropout layers were incorporated to improve stability.
</pre>
<pre>
  <h3><b>Training</b></h3>
Differentiable Augmentations: Applied to the training data to improve generalization and prevent overfitting. More information can be found <a href = "https://github.com/mit-han-lab/data-efficient-gans/blob/master/DiffAugment_pytorch.py">here</a>
Optimizer: Adam optimizer was used for both the generator and discriminator. with learning rate of 1e-3 for generator and learning rate of 1e-4 for the discriminator.
Loss Function: original DC GAN loss.
</pre>
<pre>
  <h3><b>Results</b></h3>
  the model was evaluated using Frechet Inception distance(FID). I got a FID score of 29.4831. 
  the fid was calculated by sampling 9000 examples from both original and generated distributions.
  original image
  <img src = "original.jpg">
  generated images
  <img src = "generated_image_epoch_99_batch_14401.png">
</pre>
<div>
  <img src = "output(2).giff">
</div>
  
</body>

