# Object Removal with SeamCarving

*This object removal algorithm was developed by César Caramazana and José Julián Gallardo, as the final project of a Digital Image Processing course*. 

In this notebook we implement an object removal algorithm based on Seam carving, a content-aware resizing algorithm that eliminates the pixels with the least enery in an image to perform cropping or scaling without losing meaningful information. The original paper is available here: https://www.eng.tau.ac.il/~avidan/papers/imretFinal.pdf


<h2> Description and results </h2>
We added some key modifications to the original implementation so that it takes a binary mask as an input (marking the object we want to remove) and iterates the steps of the seam carving algorithm to return a resized version of the image in which the object disappears. Due to time constrains, the algorithm as it is now only eliminates columns, although, in order to perform the resizing on the horizontal axis, a 90 degrees rotation in the input images would suffice. An example of a single seam removal is shown below:

![o0](https://github.com/CesarCaramazana/ObjectRemoval_SeamCarving/blob/main/images/seam.PNG?raw=True)

In spite of the wonders it can offer, our algorithm, as well as the original Seam Carving, cannot avoid some failure cases, in which artefacts are notorious and the results are unsatisfactory. 

![o3](https://github.com/CesarCaramazana/ObjectRemoval_SeamCarving/blob/main/images/ob_r4.PNG?raw=True)


However, we postprocessed the outputs with low-pass gaussian filters to blur these artefacts and achieve some better-looking images. The examples are shown below:

![o1](https://github.com/CesarCaramazana/ObjectRemoval_SeamCarving/blob/main/images/ob_r1.PNG?raw=True)

![o2](https://github.com/CesarCaramazana/ObjectRemoval_SeamCarving/blob/main/images/ob_r2.PNG?raw=True)

![o3](https://github.com/CesarCaramazana/ObjectRemoval_SeamCarving/blob/main/images/ob_r3.PNG?raw=True)

![o3](https://github.com/CesarCaramazana/ObjectRemoval_SeamCarving/blob/main/images/ob_r5.PNG?raw=True)


*All the images used for testing were retrieved from the public repository*: https://pixabay.com 


<h2> Code usage </h2>
The code was implemented in a Google Colab notebook <code>ObjectRemoval_SeamCarving.ipynb</code>, using the following libraries:

<ul>
  <li> Numpy </li>
  <li> Matplotlib </li>
  <li> cv2 </li>  
</ul>  

We mounted Google Drive to access some test images. The input images must be in .jpeg or .png extension. 
