# OpenCV-Contours-Detection-
Finding Contours and objects using OpenCV fucntions


### **<center><font style="color:rgb(100,109,254)">Contour Detection Part 1: The Basics </font> </center>**

Contour detection is a popular computer vision technique used for analyzing objects in an image. Contours are a useful tool for shape analysis, object detection and recognition

<center>
<img src="https://drive.google.com/uc?export=download&id=1yAoM5mODlkGIlfYn-dvCnpBPKycDsseJ" width=600>
</center>

<br>
A contour can be simply defined as a curve that joins a set of points enclosing an area having the same color or intensity. This area of uniform color or intensity forms the object that we are trying to detect, and the curve enclosing this area is the contour representing the shape of the object. So essentially, contour detection works similarly to edge-detection but with the restriction that the edges detected must form a closed path. 

In OpenCV contour detection can be performed with the help of function **`cv2.findContours()`** which we will discuss below along with the other important steps you need to perform to effectively detect the contours.
## **<font style="color:rgb(134,19,348)"> Detecting contours in an image </font>**
OpenCV saves us the trouble of having to write lengthy algorithms for contour detection and provides a handy function **`findContours()`** that analysis the [topological structure of the binary image by border following](https://www.sciencedirect.com/science/article/abs/pii/0734189X85900167), a contour detection technique developed in 1985.

The **`findContours()`** functions takes a binary image as input. The foreground is assumed to be white, and the background is assumed to be black. If that is not the case, then you can invert the image using the [**```cv2.bitwise_not()```**](https://docs.opencv.org/3.4/d2/de8/group__core__array.html#ga0002cf8b418479f4cb49a75442baee2f) function.

#### **Function Syntax:**


> [**```contours, hierarchy =   cv2.findContours(image, mode, method, contours, hierarchy, offset)```**](https://docs.opencv.org/3.4/d3/dc0/group__imgproc__shape.html#ga17ed9f5d79ae97bd4c7cf18403e1689a)

**Parameters:**

* **```image```** - It is the input image (8-bit single-channel). Non-zero pixels are treated as 1's. Zero pixels remain 0's, so the image is treated as binary. You can use compare, inRange, threshold, adaptiveThreshold, Canny, and others to create a binary image out of a grayscale or color one.

* **```mode```** - It is the contour retrieval mode, ( RETR_EXTERNAL, RETR_LIST, RETR_CCOMP, RETR_TREE )

* **```method```** - It is the contour approximation method. ( CHAIN_APPROX_NONE, CHAIN_APPROX_SIMPLE, CHAIN_APPROX_TC89_L1, etc )

* **```offset```** - It is the optional offset by which every contour point is shifted. This is useful if the contours are extracted from the image ROI, and then they should be analyzed in the whole image context.

**Returns:**

* **```contours```** - It is the detected contours. Each contour is stored as a vector of points.

* **```hierarchy```** - It is the optional output vector containing information about the image topology. It has been described in detail in the video above.

<br>

We will go through all the important parameters in detail. For now, let's detect some contours in the image that we read above.
