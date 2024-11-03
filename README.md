# Data Project course Wassterstein GAN-WP
This GitHub repository is intended for use in connection with the Data Project Exam at Aarhus University. In this README, we will briefly describe the project.

During the project, we encountered many different challenges. At the beginning, we had to familiarize ourselves with the theoretical mathematics behind GANs and then with the variant Wasserstein GAN with Gradient Penalty, also known as WGAN-GP. While getting acquainted with WGAN-GP, we also performed data cleaning on the images. The images provided by our supervisor, Ruben Pauwels, had many errors, which are also briefly described in the project description.

After going through the theory and data cleaning, we began implementing the code from the article: “Improved Training of Wasserstein GANs” by Ishaan Gulrajani, Faruk Ahmed, Martin Arjovsky, Vincent Dumoulin, and Aaron Courville (arXiv, 2017). We used the helper function Gradient Penalty from: https://github.com/aladdinpersson/Machine-Learning-Collection/tree/master/ML/Pytorch/GANs/4.%20WGAN-GP. From this, we created various generators and critics because our supervisor, Ruben, wanted images in roughly the same format as the originals. Therefore, we attempted to build a network that could produce images in a 16:9 aspect ratio, but this failed because we used some kernels that made the images blurry. Subsequently, we trained two different square WGAN-GPs; in one case, we took the original images and made them square. We trained on this, but our supervisor was not satisfied with the result, as the images became compressed and looked “strange.” A major challenge with these GANs is the number of features we can provide our model due to compute limitations and the complexity of the image details. Therefore, our supervisor recommended that we create a dataset containing only images of the teeth and build a network that generated only this type of image. The hope was that the quality would improve when the GAN focused on a smaller area, but it seemed that the well-known problem with GANs occurred, and our generator stagnated.

For this project, we used Google Colab Pro+ for compute resources. Here, we could rent an A100 GPU with 40 GB RAM. This is a large graphics card, but we were still limited by the RAM, as the number of features was only 128, which ideally should have been twice as large.

The project concluded that this type of network is not sufficient to produce synthetic images that resemble real ones. From here, the dental institute can further develop various architectures on their own. All in all, we would describe this “non-finding” as a success.

**Further Exploration of Results**

In addition to the project overview provided above, we invite you to explore the scientific paper titled "GAN_paper.pdf" located in this repository. This paper delves deeper into the findings of our project, discussing the implications of our results and offering insights into the performance of the Wasserstein GAN with Gradient Penalty (WGAN-GP) architecture. We believe that this document will provide valuable context and a more comprehensive understanding of our work.

## Results

### Generated Images

<div style="display: flex; justify-content: space-around; flex-wrap: wrap;">
  <div style="flex: 1; text-align: center; margin: 10px;">
    <img src="https://github.com/ViktorLaden/DataProjectGAN/assets/159600496/3cac0192-a8f3-42c3-a05f-28576d262b13" alt="Generated Image 1" width="300"/>
    <p>Figure 1: 512x512.</p>
  </div>
  <div style="flex: 1; text-align: center; margin: 10px;">
    <img src="https://github.com/ViktorLaden/DataProjectGAN/assets/159600496/ec8afdf6-3215-47f2-b609-8ca2f3a26cf3" alt="Generated Image 2" width="300"/>
    <p>Figure 2: 256x256.</p>
  </div>
  <div style="flex: 1; text-align: center; margin: 10px;">
    <img src="https://github.com/ViktorLaden/DataProjectGAN/assets/159600496/4bdf2d86-55c0-41b8-a1a9-431d2c55bc78" alt="Generated Image 3" width="300"/>
    <p>Figure 3: 508x287.</p>
  </div>
</div>





Results can be reproduced using the score sheet using this notebook - https://colab.research.google.com/drive/1Rz72XC767_jHZHcEu5sJKL6SLTg0JWfe#scrollTo=GElO4IfBsDjy
