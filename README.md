# CENTROID TRACKING

## INTRODUCTION

***Object tracking is the process of:***


* Taking an initial set of object detections (such as an input set of bounding box coordinates).

* Creating a unique ID for each of the initial detections.

* And then tracking each of the objects as they move around frames in a video, maintaining the assignment of unique IDs


Object Tracking
:-------------------------:
![](assets/README/main.gif)


Furthermore, object tracking allows us to apply a unique ID to each tracked object, making it possible for us to count unique objects in a video. Object tracking is paramount to building a person counter.

***An ideal object tracking algorithm will:***

* Only require the object detection phase once (i.e., when the object is initially detected)

* Will be extremely fast — much faster than running the actual object detector itself

* Be able to handle when the tracked object “disappears” or moves outside the boundaries of the video frame

* Be robust to occlusion

* Be able to pick up objects it has “lost” in between frames


This is a tall order for any computer vision or image processing algorithm and there are a variety of tricks we can play to help improve our object trackers.

## THE FUNDAMENTALS OF CENTROID-BASED OBJECT TRACKING

***Centroid-based*** tracking is an easy to understand, yet highly effective tracking algorithm. There are also more advanced ***kernel-based*** and ***correlation-based*** tracking algorithms which are not considered in this project.

This object tracking algorithm is called centroid tracking as it relies on the Euclidean distance between (1) existing object centroids (i.e., objects the centroid tracker has already seen before) and (2) new object centroids between subsequent frames in a video.

***The centroid tracking algorithm is a multi-step process.***

### Step #1: Accept bounding box coordinates and compute centroids.
















































