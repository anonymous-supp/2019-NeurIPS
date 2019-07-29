# 2019-NeurIPS
anonymous supplementary material

## Experimental setup
 In this paper, we have compared our method with three image-to-image translation models ([CycleGAN](), [MUNIT]() and [DRIT]()), and also two image steganography methods ([Steganography]() and [HiDDeN]()). Please note that all their methods belong to `symmetric image steganography (encryption)` methods, only our method could perform `asymmetric image steganography (encryption)`.
 
 For all the experiments, we all use facial images and flower images as cover images, and regard images from SVHN dataset and more complex images from Cat2dog dataset. For the flower images, we randomly use seven different kinds of flowers from [102flowers](http://www.robots.ox.ac.uk/~vgg/data/flowers/102/).
 And there are 878 (704 for training and 174 for testing) flower images in total, in order to balance the training dataset between two domains, we randomly select 695 facial images from [CelebA](http://mmlab.ie.cuhk.edu.hk/projects/CelebA.html). In order to evaluate the model, we randomly select 5000 facial images from CelebA for our method. 
 
 As for the secret information image (simple number information and complex information images),
 we randomly select 1000 number images for the training stage. To obtain quantitative comparison, we could randomly paste the remaining number image to the testing cover images at different positions. Consider there are infinite combinations to get different composite images, We just randomly paste one unseen number image to testing cover images at center location to get composite images at testing stage. Please note we compute all the quantitative results of above mentioned methods through `same testing composite images`.
  For the complex information images, we inherit the Cat2dog from [DRIT](), we follow their division (771 training and 100 testing images for cat, 1264 training and 100 testing images for dog). Following the same operation to obtain testing composite images, Please note that we compute the quantitative results of all the above mentioned methods through `same testing composite images`.
 
 For the training of image-to-image translation models, we randomly pick up one secret message image from the training message images at 50% chance. If yes, we randomly paste the secret image to cover image at different position, then we regard the composite as the final input of generators. If not, we just use the raw cover image as input image. Please note all the real samples for discriminator are the raw input images, we don't paste the message image to them.
 
 For the training of the image steganography methods: Steganography and HiDDeN. For Steganography, we follow the instructions of https://github.com/harveyslash/Deep-Steganography. For HiDDeN, we follow the instructions of https://github.com/ando-khachatryan/HiDDeN. For fair comparison, here we use the same above mentioned training images and testing images. 

## Training details
In order to make our model robust and generative, we just paste the message image to input image at 50% chance during the training stage, this operation could force model to concentrate on the local message information.   
### Losses
#### Local loss
In order to reconstruct clearer message image, we design a local loss to compute the pixel-wise loss between the local regions to paste the message image.
#### Information loss
In order to guarantee that we can only reconstruct required message using true private key. So we don't compute the cycle-consistency loss.

### Key generator function K
Here we use a CNN architecture with 7 layers (6 Conv-Instance-LeakyReLU modules and 1 fc layer) to distribute paired public and private keys. For public keys, we regard the cover image and the disentangled representation (public disguise) of one random image from another domain as public key, while we regard the disentangled representation of the the same cover image as paired private key.
So the CNN architecture provides an implicit coupling relationship between public key and private key. We optimize the key generator with classification loss and hope to obtain the disentangled representation of different layers.

### Mapping function F and G
We optimized the F and G together by the final objective function.     

### Hyper-parameter
The final objective function 

## Complex information encryption
### Qualitative comparison of complex information encryption of using size `64*64`

<table class="tg">
  <tr>
    <th class="tg-0pky">Methods</th>
    <th class="tg-0pky">FID</th>
    <th class="tg-0pky">Encryption(LPIPS/MSE)</th>
    <th class="tg-0pky">MSE</th>
    <th class="tg-0lax">RMSE</th>
    <th class="tg-0lax">PSNR</th>
    <th class="tg-0lax">SSIM</th>
    <th class="tg-0lax">LPIPS</th>
  </tr>
  <tr>
    <td class="tg-0pky">CycleGAN</td>
    <td class="tg-0pky">189.5232</td>
    <td class="tg-0pky">0.5231/0.0912</td>
    <td class="tg-0pky">0.0096</td>
    <td class="tg-0lax">0.1269</td>
    <td class="tg-0lax">19.3523</td>
    <td class="tg-0lax">0.9754</td>
    <td class="tg-0lax">0.3128</td>
  </tr>
  <tr>
    <td class="tg-0pky">MUNIT</td>
    <td class="tg-0pky">225.1347</td>
    <td class="tg-0pky">0.6212/0.0723</td>
    <td class="tg-0pky">0.0097</td>
    <td class="tg-0lax">0.1272</td>
    <td class="tg-0lax">18.6742</td>
    <td class="tg-0lax">0.9637</td>
    <td class="tg-0lax">0.3312</td>
  </tr>
  <tr>
    <td class="tg-0pky">DRIT</td>
    <td class="tg-0pky">217.3423</td>
    <td class="tg-0pky">0.5124/0.0852</td>
    <td class="tg-0pky">0.0091</td>
    <td class="tg-0lax">0.1042</td>
    <td class="tg-0lax">19.0313</td>
    <td class="tg-0lax">0.9673</td>
    <td class="tg-0lax">0.3042</td>
  </tr>
  <tr>
    <td class="tg-0pky">Steganography</td>
    <td class="tg-0pky">212.5234</td>
    <td class="tg-0pky">0.5341/0.0634</td>
    <td class="tg-0pky">0.0089</td>
    <td class="tg-0lax">0.0975</td>
    <td class="tg-0lax">18.9933</td>
    <td class="tg-0lax">0.9698</td>
    <td class="tg-0lax">0.2871</td>
  </tr>
  <tr>
    <td class="tg-0pky">EncryptGAN</td>
    <td class="tg-uog8">155.1446</td>
    <td class="tg-uog8">0.7670/0.0967</td>
    <td class="tg-uog8">0.0084</td>
    <td class="tg-uca5">0.0901</td>
    <td class="tg-uca5">20.9072</td>
    <td class="tg-uca5">0.9710</td>
    <td class="tg-uca5">0.2631</td>
  </tr>
</table>


### Qualitative comparison of complex information encryption of using size `128*128`
<table class="tg">
  <tr>
    <th class="tg-0pky">Methods</th>
    <th class="tg-0pky">FID</th>
    <th class="tg-0pky">Encryption(LPIPS/MSE)</th>
    <th class="tg-0pky">MSE</th>
    <th class="tg-0pky">RMSE</th>
    <th class="tg-0pky">PSNR</th>
    <th class="tg-0pky">SSIM</th>
    <th class="tg-0pky">LPIPS</th>
  </tr>
  <tr>
    <td class="tg-0pky">CycleGAN</td>
    <td class="tg-0pky">165.6343</td>
    <td class="tg-0pky">0.4105/0.1024</td>
    <td class="tg-0pky">0.0115</td>
    <td class="tg-0pky">0.1209</td>
    <td class="tg-0pky">21.3641</td>
    <td class="tg-0pky">0.9246</td>
    <td class="tg-0pky">0.3173</td>
  </tr>
  <tr>
    <td class="tg-0pky">MUNIT</td>
    <td class="tg-0pky">221.6354</td>
    <td class="tg-0pky">0.3367/0.0824</td>
    <td class="tg-0pky">0.0124</td>
    <td class="tg-0pky">0.1222</td>
    <td class="tg-0pky">19.6723</td>
    <td class="tg-0pky">0.9423</td>
    <td class="tg-0pky">0.3418</td>
  </tr>
  <tr>
    <td class="tg-0pky">DRIT</td>
    <td class="tg-0pky">182.5341</td>
    <td class="tg-0pky">0.3135/0.0942</td>
    <td class="tg-0pky">0.0102</td>
    <td class="tg-0pky">0.1211</td>
    <td class="tg-0pky">19.2341</td>
    <td class="tg-0pky">0.9219</td>
    <td class="tg-0pky">0.3174</td>
  </tr>
  <tr>
    <td class="tg-0pky">Steganography</td>
    <td class="tg-0pky">198.2543</td>
    <td class="tg-0pky">0.3112/0.1013</td>
    <td class="tg-0pky">0.0128</td>
    <td class="tg-0pky">0.1226</td>
    <td class="tg-0pky">19.9832</td>
    <td class="tg-0pky">0.9473</td>
    <td class="tg-0pky">0.2941</td>
  </tr>
  <tr>
    <td class="tg-0pky">EncryptGAN</td>
    <td class="tg-uog8">140.7061</td>
    <td class="tg-uog8">0.4190/0.1214</td>
    <td class="tg-uog8">0.0068</td>
    <td class="tg-uog8">0.0808</td>
    <td class="tg-uog8">22.0137</td>
    <td class="tg-uog8">0.9475</td>
    <td class="tg-uog8">0.2854</td>
  </tr>
</table>

## More results

### Different positions (`64*64`)

### Different positions (`128*128`)