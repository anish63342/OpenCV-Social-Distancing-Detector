<h1 align="left">
    OpenCV-Social Distancing Detector
</h1>

A social distancing detector built with OpenCV.

<h2> Introduction<span style='font-size:100px;'></h2>	
<p>
    Coronavirus disease 2019 (COVID-19) is a contagious disease caused by severe acute respiratory syndrome coronavirus 2(SARS-CoV-2).
The first known case was identified in Wuhan, China, in December 2019. The disease has since spread worldwide, leading to an ongoing pandemic.
</p>
<p>
Social distancing is a method used to control the spread of contagious diseases. It implies that people physically distance themselves from one another, reducing close contact, and thereby reducing the spread of a contagious disease (such as the COVID-19 Disease).
</p>

<p align="center">
  <img src="https://blog.aginglifecare.org/wp-content/uploads/2020/03/Social-Distancing-Coronavirus-Poster-1.png">
</p>

<p align="center">
   Social distancing is crucial to the prevention of the spread of disease.
</p>

* Use case: counting the number of people in the stores/buildings/shopping malls etc., in real-time.
* Monitoring the physical distance between people to prevent the further spread of COVID-19.
* Acts as a measure to tackle COVID-19.

## Working:

### Object detection:

* We will be using YOLOv3, trained on COCO dataset for object detection.
* In general, single-stage detectors like YOLO tend to be less accurate than two-stage detectors (R-CNN) but are significantly faster.
* YOLO treats object detection as a regression problem, taking a given input image and simultaneously learning bounding box coordinates and corresponding class label probabilities.
* It is used to return the person prediction probability, bounding box coordinates for the detection, and the centroid of the person.

### Distance calculation:

* NMS (Non-maxima suppression) is also used to reduce overlapping bounding boxes to only a single bounding box, thus representing the true detection of the object. Having overlapping boxes is not exactly practical and ideal, especially if we need to count the number of objects in an image.
* Euclidean distance is then computed between all pairs of the returned centroids. Simply, a centroid is the center of a bounding box.
* Based on these pairwise distances, we check to see if any two people are less than/close to 'N' pixels apart.



## Output:
![raw-vid](res/demo0.gif "Unprocessed video") ![processed-vid](res/demo1.gif "Processed video")
