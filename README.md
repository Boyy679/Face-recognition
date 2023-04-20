# Face Recognition

This project mainly has 4 sections to do face recognition:

* Section1: Face Feature Extraction
* Section2: Image Face Detection
* Section3: Web Camera Face Detection
* Section4: Video Face Detection

> **Section1：Face Feature Extraction**

This part shows the basic face recognition principles, including facial features and Facial embedding.

- **Facial features:** 

  Basic ides in facial recognition in normal face is come up with 68 specific points(landmarks), including the chin, left eyebrow, right eyebrow, nose bridge, nose tip, left eye, right eye, top lip and bottom lip.

![image-20230420113930714](C:/Users/think/Desktop/fyp海报/Face-recognition/a-Face-Feature-Extraction/data/image-20230420113930714.png)

We use bidden face as example to finish this job. This face will look like the following picture after 	face feature extract.

![image-20230420114200128](C:/Users/think/Desktop/fyp海报/Face-recognition/a-Face-Feature-Extraction/data/image-20230420114200128.png)

- **Facial Embedding: **

  In this part, each person's face information will store as a vector.

  - Compare two face distance
    - faces with a distance of 0.6 or less should be a match.
    - using a 0.55 cutoff (if want to be more strict; cutoff would reduce false positive matches at the risk of more false negatives)

  For example, we calculate the distance between Biden, Trump and Obama(by using TSNE):

  ![distance](C:/Users/think/Desktop/fyp海报/Face-recognition/a-Face-Feature-Extraction/data/distance.png)

  





















