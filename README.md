# Hand-Gesture-Recognition
Recognizing Hand Gestures using real time and recorded videos

### Objective
- To detect hand gestures using Computer Vision techniques
- Detecting the number of fingers correctly using Python program
- 2 styles of input - real time video and recorded video

### Explanation of Code
#### Concept of Running Averages:
- Efficient method to to separate foreground from background. 
- Initializing the background with respect to current frame for background subtraction.
- Calculating Running Average over background model and current frame:         
  cv2.accumulateWeighted() ->  It calculates the weighted sum of the input image src and the accumulator dst so that dst becomes a running average of a frame sequence.
  dst(x,y)=(1−a).dst(x,y)+a.src(x,y)

#### Segmentation:
- The purpose of image segmentation is to partition an image into meaningful regions.
- Finding the absolute difference between background and current frame
- Thresholding - binarization of an image - to convert a grayscale image to a binary image, where the pixels are either 0 or 255.
- Finding Contours - a curve joining all the continuous points along the boundary, having the same color or intensity - for shape analysis and object recognition and detection.

#### Counting Fingers:
- Step1: Find the convex hull of the segmented hand region (which is a contour) and compute the most extreme points in the convex hull 
- Step 2: Find the center of palm using these extremes points in the convex hull.
- Step 3: Using the palm’s center, construct a circle with the maximum Euclidean Distance (between the palm’s center and the extreme points) as radius.
- Step 4: Perform bitwise AND operation between the thresholded hand image (frame) and the circular ROI (mask). 
