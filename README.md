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
