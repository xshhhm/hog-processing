# Hog-Processing #

Histogram of Oriented Gradients (_HOG_) is a popular method for object detection, particularly suitable for pedestrians detection.
The method is based on the evaluation of histograms calculated on the basis of the orientation of the gradients of the input image. The idea is that the edges and the shapes of objects can be well characterized by the intensity of individual local gradients. Computation of each histogram is obtained by dividing the image into a grid of cells and for each of them is computed a histogram of gradients. Then the cells are grouped into regions called blocks. In addition, to release the response by the terms of brightness, can be useful normalize individual blocks.

From information of the individual blocks you get a descriptor that will be used for detection. The above operations are performed on windows of finite size that analyze the image at multiple scales. For each window is then obtained a descriptor that is then given to a linear SVM classifier that provides predictions about the presence or absence of a pedestrian.

Being the construction procedures of individual descriptors independent of each other, you can run them simultaneously with a multi-threading system. In this way you get a significant performance improvement.

The robustness of the algorithm used (SVM algorithm) and accurate image scanning at multiple scales, often produce a dense group of detection windows for each object, then a merger is required (mean-shift) that brings up to a final identification window.



---

### References ###

Navneet Dalal and Bill Triggs. Histograms of oriented gradients for human detection. In Cordelia Schmid, Stefano Soatto, and Carlo Tomasi, editors, International Conference on Computer Vision and Pattern Recognition, volume 2, pages 886-893, INRIA Rhone-Alpes, ZIRST-655, av. de l'Europe, Montbonnot-38334, June 2005