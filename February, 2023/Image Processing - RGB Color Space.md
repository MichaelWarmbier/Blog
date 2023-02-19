# <p align="center">Image Processing: RGB Color Space</p>

<p align="center"><strong>February 18th, 2023</strong></p>

###### <p align="center">© Michael Warmbier</p><br><br>

&emsp;&emsp;Recently, I've begun attending a class where I've been learning <em>Image Processing</em>. I've only just started, and a lot of the topics are interesting enough to write blog posts about on their own. To start, I wanted to discuss some methods I made using the _Python_ `PIL`, or **Pillow** library. I made these to separate the RGB color spaces to quickly make observations about different images, as well as for future projects.

To start, here are the library dependencies I used for this specific set of methods:

```py
# Image manipulation
from PIL import Image
# Formulas
import numpy as np
```

I use more libraries overall, but this should cover these specific dependencies. Also, all of these examples were made with and programmed on _Repl.it_.

First up, we have a method that will divide an image of three channels, like RGB and HSV/HSL, into three separate channels of the color space, and save those channel as a representation of only **L**, or grayscale.

```py
def splitChannels(image): 
  sW, sH = image.size;                                  # Store image size dimensions
  pX = image.load();                                    # Create a pointer to image pixels
  Channel = [                                           # Initialize three new grayscale images
    Image.new('L', (sW, sH), 0),
    Image.new('L', (sW, sH), 0),
    Image.new('L', (sW, sH), 0)
  ];
  CPx = [];                                             # Create and load three new pointers for these images' pixels
  for v in range(3): CPx.append(Channel[v].load());
    
  for index in range(3):                                # Iterate each color into one image each, by pixel
    for x in range(sW):
      for y in range(sH):
        CPx[index][x, y] = pX[x, y][index];
  return Channel;                                       # Return all three images
```

Next, a method responsible for converting that grayscale data into its specific color representation. I separated these methods into two in case of the likely scenario that I want to compare the grayscale and color versions of images.

```py
def L_To_RGB(image, color):                                       
  sW, sH = image.size;                                    # Store image size dimensions
  pX = image.load();                                      # Create a pointer to image pixels
  Result = Image.new("RGB", (sW, sH), 0);                 # Create a new image of the same size
  rPx = Result.load();                                    # Create a pointer to new image's pixels

  # Iterate each pixel in grayscale and move over to new image as only equivalent color channel provided.
  for x in range(sW):                                      
    for y in range(sH):   
      if (color.lower()  == 'r'): rPx[x, y] = (pX[x, y], 0, 0);
      if (color.lower()  == 'g'): rPx[x, y] = (0, pX[x, y], 0);
      if (color.lower()  == 'b'): rPx[x, y] = (0, 0, pX[x, y]);
  return Result;                                          # Return single image of color
```

Utilizing these two methods, I made some examples of interesting images that I think many would appreciate:

<p align="center"><img src="https://cdn.discordapp.com/attachments/1071220323581702144/1076623230078558248/index.webp"></p>

#### <p align="center">Original image before channel split; RGB Venn diagram.</p>

<p align="center"><img src="https://cdn.discordapp.com/attachments/1071220323581702144/1076623091846877285/image.png"></p>

##### <p align="center">Image divided by color space and placed side-by-side.</p>

<br>
  

<p align="center"><img src="https://cdn.discordapp.com/attachments/1065328426032058470/1076795711020072960/image.png"></p>

#### <p align="center">An image of _New York City_. From left to right: original, G color space, G as grayscale.</p>
##### <p align="center">Photograph by guvendemir, iStockphoto; Taken from National Geographic website.</p>

<br>

<p align="center"><img src="https://media.discordapp.net/attachments/1071220323581702144/1076624438197497967/image.png?width=1080&height=304"></p>

#### <p align="center">Generic rainbow of colors. From left to right: original, blue values.</p>

<br><br>

&emsp;&emsp;Personally, I think being able to manipulate colors and represent them like this is incredibly interesting. There's a wide variety of use for extracting color information; most notably image enhancement observational data. 

Regardless of its immediate use, being able to represent color as information and then portray that information in a visible representation akin to its origin is not only incredibly fascinating, but objectively educational.
