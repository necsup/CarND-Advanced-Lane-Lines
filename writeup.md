<div align='center'>
    <h1>Advanced Lane Finding</h1>
    <h3>Philip Necsulescu, 05.12.2020</h3>
</div>

## Writeup / README

### Provide a Writeup / README that includes all the rubric points and how you addressed each one. You can submit your writeup as markdown or pdf. Here is a template writeup for this project you can use as a guide and a starting point.


## Camera Calibration

### Briefly state how you computed the camera matrix and distortion coefficients. Provide an example of a distortion corrected calibration image.


## Pipeline (test images)

### Provide an example of a distortion-corrected image.

### Describe how (and identify where in your code) you used color transforms, gradients or other methods to create a thresholded binary image. Provide an example of a binary image result.

I lowered the s_binary_min threshold from 170 used in the course to 150 to be able to get the lane covered by the tree's shadow
narrowed the gradiant thresholds to [40 80] to get avoid noise/dirt from the middle of the road

### Describe how (and identify where in your code) you performed a perspective transform and provide an example of a transformed image.

### Describe how (and identify where in your code) you identified lane-line pixels and fit their positions with a polynomial?

### Describe how (and identify where in your code) you calculated the radius of curvature of the lane and the position of the vehicle with respect to center.

### Provide an example image of your result plotted back down onto the road such that the lane area is identified clearly.


## Pipeline (video)

### Provide a link to your final video output. Your pipeline should perform reasonably well on the entire project video (wobbly lines are ok but no catastrophic failures that would cause the car to drive off the road!)


## Discussion

### Briefly discuss any problems / issues you faced in your implementation of this project. Where will your pipeline likely fail? What could you do to make it more robust?

    A white car or large objects might end up in front of the car and be idenfied as part of the lane. Using a maximum width might help as lane markings are relatively narrow.

    Choosing source points has to be relatively close to car and not far down the horizon so that curves don't have as large of an impact.
### Issues encountered and solutions

 - cv2.imread imports in BGR, plt (plt.imshow and plt.write) use RGB.
     - Solution: use cv2.cvtColor(image, cv2.COLOR_BGR2RGB)
 - Dark/dirty lanes