 # Autonomous Car

-->Autonomous Car is designed for Self driving with advanced driving sense control in all time and sense the diff b/w car back & traf?c lights (RED).It will also sense all type of sign board instructions and lane detection. It's still under progress!

## Table of Contents
* [General Information](#general-information)
* [Softwares](#Softwares)
* [Setup_Used](#Setup_Used)
* [Features](#features)
* [Inspiration](#inspiration)
* [License](#license)
* [Conclusion](#Conclusion)

## General Information
 In this project, MATLAB is used as an Image Processing Tool to detect Lanes on the road. The following techniques are used for lane detection. 
 
 • Color Masking
 • Canny Edge Detection
 • Gamma Correction 
 • Region of Interest Selection
 • Hough Transform Line detection  

## Softwares
--> Matlab RA 2018


## Setup_Used

--> Pre-processing the Image
    The first step is to import the video file and initialize the variables to be use din the code. Some variables are also imported from the .mat file to be used in the code. 

--> frames one by one
    First the frame is read and them filtered using a Gaussian Filter.
    
    ![alt text](https://github.com/Piraicv/Autonomous-car/blob/main/Output/Gaussian%20Filtered%20Img.jpg)

--> Masking the image for White and Yellow Color
    The frame is masked with yellow and white color to detect the lane lines perfectly.
    
    Yellow mask
    ![alt text](https://github.com/Piraicv/Autonomous-car/blob/main/Output/Yellow%20Mask%20Img.jpg)

    White mask
    ![alt text](https://github.com/Piraicv/Autonomous-car/blob/main/Output/White%20Mask%20Img.jpg)


--> Edge Detection
    In this section, edges are obtained from the masked image and closed edges with smaller areas are neglected.

--> Extraction of Region of Interest
    As guided in the pipeline for the implementation of the project 1 the region of interest is extracted using the 'roipoly' function and selecting the points from the frame.

--> Hough Transform
    In this section I have used the hough function to get the hough transfrom of the binary edge detected image, which gives us the hough values and then I have plotted the         hough plot. as shown in the figure below.
    
    hough plot
    ![alt text](https://github.com/Piraicv/Autonomous-car/blob/main/Output/Hough%20lines%20found%20in%20image.jpg)
    hough peak found for yellow
    ![alt text](https://github.com/Piraicv/Autonomous-car/blob/main/Output/Hough%20peaks%20found%20for%20yellow%20lines.jpg)
    hough peak found for white
    ![alt text](https://github.com/Piraicv/Autonomous-car/blob/main/Output/Hough%20peaks%20found%20for%20white%20lines.jpg)
    
--> Lane Detection
   In this section, I have predicted where to turn by looking at the vanishing point found from the extrapolated lines.
   
   ![alt text](https://github.com/Piraicv/Autonomous-car/blob/main/Output/Lane%20Detection.jpg)

--> Gamma correction
    Here gamma correction is performed is due to encode and decode luminance or tristimulus values in video. Images which are not properly corrected can look either bleached     out, or too dark. Trying to reproduce colors accurately also requires some knowledge of gamma and avoid img over exposed. 


## Features

* Lane detection
* Sign instructions
* Day & Night

## Inspiration
I took a lot of inspiration from:
- [Leah Linder](http://leah-lindner.com/) Portfolio
- [Hugo Peters](http://hugo.fyi/) Portfolio

## License
> You can check out the full license [here](./LICENSE.md)

This project is licensed under the terms of the **MIT** license.

## Conclusion

The project was successful in that the video images clearly show the lane lines are detected properly and lines are very smoothly handled. But this project is under development for several logics works.
It only detects the straight lane lines. It's still not confident in handling the deep curve lanes (or the curvature of lanes). We'll need to use perspective transformation and also poly fitting lane lines rather than fitting to straight lines. 
Identification of Red light (danger light and traffic light is still on process). Devloper are welcomes to develop this project. 

