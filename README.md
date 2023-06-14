<h2 align = center>Horizon-Detection</h2>

### Problem Statement
---

An algorithm that can differentiate between sky pixels and other pixels to create a horizon that can be used for further image registration and processing.
 
 ### Motivation
 ---
 
Horizon detection in still images or video sequences contributes to the applications like image understanding, image registration and image quality enhancement. These results can be used to aid UAV and also be used in geology for the analysis of rock formation and layer detection.

### Proposed Solution
---

Using an edge-based detector the principle edge which separates the sky from the rest of the image can be found. The detector uses the concepts of canny edge detector and Hough map transforms. Processing the image through a canny edge detector results in an edge image that contains the significant edges. Transforming the edge image using the Hough map transform straight lines can be found through which the principle edge line can be found.

### Workflow Diagram
---

<img src = "https://github.com/msc-1729/Horizon-Detection/blob/main/assets/Hough%20Transform%20Workflow.png" />

### Implementation
---

The given image pixels are divided into two gaussian distributions sky and ground in RGB space and then a line segment which separates these two is found by maximizing the optimization criteria. By using the ResultantDifference function and HorizonDetection function the sky and ground pixels are categorized based on the slopes and intercepts defined, based on the formula derived from the Hough line transform technique. The HorizonDetection function consists of the code that is used to calculate the values of the determinant and eigenvalues of the covariance matrices of sky and ground pixel arrays. These values are in turn used for defining an optimization term 'r' that is maximized and the values of slope and intercept of that particular iteration is returned. These values are used to draw a best fitting line in the input image which is resulted output image that contains the horizon of the image.

### Results
---

##### INPUT IMAGE

<img src = "https://github.com/msc-1729/Horizon-Detection/blob/main/assets/Horizon%20Detection%20Input%20Image.png" />

##### OUTPUT IMAGE

<img src= "https://github.com/msc-1729/Horizon-Detection/blob/main/assets/Horizon%20Detection%20Output%20Image.png" />

### Future Scope 
---

The accuracy of the project can be increased by combining both the edge and color detection concepts together to make the project more reliable. This can be integrated woth the projects which provide visual assistance for the unmanned aerial vehicle and in image registration processes.
