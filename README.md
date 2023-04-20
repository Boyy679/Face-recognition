# Face Recognition

This project mainly has 5 sections to do face recognition:

* Section1: Face Feature Extraction
* Section2: Image Face Detection
* Section3: Web Camera Face Detection
* Section4: Video Face Classify
* Section5: Video Face detection

### Section1：Face Feature Extraction

This part shows the basic face recognition principles, including facial features and Facial embedding.

> **Facial features:** 

Basic ides in facial recognition in normal face is come up with 68 specific points(landmarks), including the chin, left eyebrow, right eyebrow, nose bridge, nose tip, left eye, right eye, top lip and bottom lip.

<div align=center><img src="a-Face-Feature-Extraction/data/image-20230420113930714.png" alt="image-20230420113930714" width="30%" height="30%" /></div>

We use bidden face as example to finish this job. This face will look like the following picture after face feature extract.

<div align=center><img src="a-Face-Feature-Extraction/data/image-20230420114200128.png" alt="image-20230420114200128" width="25%" height="25%"  /></div>

> **Facial Embedding:** 

In this part, each person's face information will store as a *vector*.

- Compare two face distance
  - faces with a distance of **0.6 or less** should be a match.
  - using a **0.55 cutoff** (if want to be more strict; cutoff would reduce false positive matches at the risk of more false negatives)

For example, we calculate the distance between Biden, Trump and Obama(by using *TSNE*):

<div align=center><img src="a-Face-Feature-Extraction/data/distance.png" alt="distance" width="35%" height="35%"/></div>

### Section2: Image Face Detection

This is a section by using KNN and SVM classifier to do face recognition.

* KNN model:
  * KNN classifier is first trained on a set of labeled (known) faces and can then predict the person in an unknown image by finding the k most similar faces (images with closet face-features under ***euclidean distance***) in its training set, and performing a majority ***vote*** (possibly weighted) on their label. This implementation uses a *weighted vote*, such that the votes of closer-neighbors are weighted more heavily. This implementation uses a weighted vote, such that the votes of closer-neighbors are weighted more heavily.
  * **Example:** if k=3, and the five closest face images to the given image in the training set are three image of Biden and two images of Obama, The result would be 'Biden'.
  * How to use:
    * Organize the set of images of the people you want to recognize in a single directory with a sub-directory for each known person.
    * Then, call the 'train' function with the appropriate parameters. Make sure to pass in the '*model_save_path*' if you want to save the model to disk so you can re-use the model without having to re-train it.
    * Call '*predict*' and pass in your trained model to recognize the people in an unknown image.

```
Directory tree:
1. train_dir/Biden/xxx.jpg ...
2. train_dir/Barack Obama/yyy.jpg ...
3. train_dir/Donald Trump/zzz.jpg ...
```

> **3D PCA**

Put Obama, Biden, Trump, Gates, Zuckerberg and Pages' images visualized by 3D PCA 

<div align=center><img src="b-image-face-detection\data\3DPCA.png" alt="3DPCA" style="zoom:67%;" width="55%" height="55%"/></div>

> Face detection

<div align=center><img src="b-image-face-detection\data\detectedimage.png" alt="detectedimage" width="35%" height="35%" /></div>

This is a example for recognize Obama's face.

### Section3: Web Camera Face Detection

We ALSO can use PC camera to achieve face detection.

You need to upload one images of the face you want to recognition and rename the images' name as the people's name.

```Directory tree:
Tree
1. data/Biden.jpg 
		Barack Obama.jpg
		Donald Trump.jpg
		... ...
```

When you run the code, the PC camera will open, and if you don't input some face images you want to detection into the data dictionary, it will detection as **unknown**, like the following.

<div align=center><img src="c-webcamera-face-detection\note\unknown.png" alt="unknown" width="35%" height="35%" /></div>

### Section4: Video Face Classify

We input a test video for the program and use T-SNE transform to do a face classify.

Then, we see the face encoding distribution in this video:

<div align=center><img src="d-video-face-classify\data\plot.png" alt="plot" width="40%" height="40%" /></div>

Because in this test video, mainly has 2 people, so we can clearly to see 2 point clusters.

### Section5: Video Face Detection

This is a video face detect code which can used to label the faces in the video and output. 

This project use *Little Sheldon* video clip to do this part, the dataset like the following tree:

```
Tree
Dataset/George
			01.jpg
			02.jpg
			...
		Georgie
			01.jpg
			02.jpg
			...
		Librarian
			01.jpg
			02.jpg
			...
		Little Shelton
			01.jpg
			02.jpg
			...
		... ...
```

The output of like the following one, left is input and the right is output result:

<div align=center><img src="e-video-face-detection\data\image-20230420233342596.png" alt="image-20230420233342596" style="zoom:80%;" /></div>

And the face detection for *little Shelton*

<div align=center><img src="e-video-face-detection\data\image-20230420233655343.png" alt="image-20230420233655343"  /></div>







