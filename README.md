***Description*** This is the second iteration of a machine-learning model for facial recognition. The first was using HC, Haar-Cascading, which utilized a sub frame-by-frame analysis to see if the smaller frame matches a database of current comparisions and highlights them. 
While that model worked well for distinct features (face, eyes), it struggled with harder to decipher features (mouth). I hope to fix this with using Histogram of Oriented Gradients.

***Histogram of Oriented Gradients***
From my readings, HOG is fed an grey-scale image, then utilizes selection of specific portions of the image and breaks down the image in a 1:2 ratio portion. 
It then takes each individual part of the 2:1, and further breaks it down into a 8x8 pixel grid. In each of these pixels, the difference between the pixel above and below the box is calculated (Gx) and left and right (Gy). 
These values are then used to find the overall gradient difference using magnitude calculation (distance formula) and angle calculation (arctan). The Gx and Gy values are also normalized (division by the magnitude) in order to hold differences the same if the original image is changes. 
After this calculation is done for all pixels in the 8x8, they are seperated into 9 "bins" based on angle. The bids span 20 degrees (0˚-20˚, 21-40˚, etc.), and the magnitutde of that corresponding pixel is then distributed between the bins. 
These are then used to create vectors to each of the degrees. This gradient vector graph is present for each 8x8 pixel-grid, and shows the difference between 2 grey-scale values, with higher-brightness gradients showing key differences and the complexitiy of the gradient showing the difference in contrast.

***Credit****
*   https://builtin.com/articles/histogram-of-oriented-gradients
