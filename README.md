# Real-time-Pest-detetcion-using-OpenCV
Detecting pests in real-time using OpenCV involves leveraging computer vision techniques to identify and track specific pest species. 
Readme
This module reads all images from the images/input folder. For each image the following 
steps are processed:
1. The image is buffered in RGB and HSV format.
image = PlantDetection(folder, filename)
2. The outlines of the plants are found via color detection and then the found outlines 
are edited.
image.findPlants()
3. The search for points on the plant has started. There are three methods for this:
1. only red points are searched. This procedure is very restrictive.
image.findRedStickers(log)
2. all colors except green are recognized as points. This procedure is rather 
inaccurate, since also plant parts can be recognized.
image.findStickers(log)
3. only white dots are searched for. Here, too, parts of the plant can be falsely 
detected as dots.
image.findSmallSpots(log)
4. The found points are drawn in pink in the original image
image.showResultImage(white)
For each run, a log file documents which detection method found how many pixels.
Requirements
The following packages are required:
skimage
numpy
datetime
cv2
os
40
Usage
Load an image
image = PlantDetection(folder, filename)
Remove everything except the plants from the loaded image
image.findPlants()
Pepare new logfile entry
log.write("File: " + filename + "\n")
Find red color in loaded image
red = image.findRedStickers(log)
Find all colors except green in loaded image
allColors = image.findStickers(log)
Find white color in loaded image
white = image.findSmallSpots(log)
Print result
image.showResultImage(x)
x can be red, allColors or white
