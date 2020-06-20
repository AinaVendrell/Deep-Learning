# Simpson face generator using GAN and VAE

Our main goal was to generate some realistic new characters of Simposon using two types of networks the Variational Autoencoder and the Generative Adversarial Network. We have done 3 test, one test with VAE and 2 test with GAN, each test with a different GAN structure. In the results part we can see the new generated faces. 

## Instructions

1. Download [Simpson Dataset](https://www.kaggle.com/kostastokis/simpsons-faces)
2. Resize images to 64x64, we have used 
```python
#!/usr/bin/python
from PIL import Image
import os, sys

path = "/content/drive/My Drive/Deep_Learning_FP/simpson/"
dirs = os.listdir( path )

def resize():
  for item in dirs:
    if os.path.isfile(path+item):
      print(path+item)
      im = Image.open(path+item)
      f, e = os.path.splitext(path+item)
      imResize = im.resize((64,64), Image.ANTIALIAS)
      imResize.save(f+'.png', 'png', quality=80)
resize() 
```
3. Execute the code to train the CNN or use the two ckpt files in the Results folder that contain the GAN1 and the VAE already trained. They can be used in the last part of the codes to visualize the results.

## Results

### GAN1
<p align="center">
  <img src="Results/GAN1.png" width="300">
</p>

### VAE
<p align="center">
  <img src="Results/GAN1.png" width="300">
</p>

## Conclusions

Using VAE the results obtained are very blurry, however we can see good results with very few epoches.

Using the first version of GAN we have obtained a better result in terms of resolution but we are able to see some artifacts due to the face variability. Better results could be achieve with more epoches. 

Using the second version of GAN we have obtained the poorest results. It does not find an equilibration point and the results are not the desired.


