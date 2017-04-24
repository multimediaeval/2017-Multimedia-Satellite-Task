# 2017-Multimedia-Satellite-Task

## What is this task about?

The multimedia satellite task requires participants to retrieve and link multimedia content from social media streams (Flickr, Twitter, Wikipedia) of events that can be remotely sensed such as flooding, fires, land clearing, etc. to satellite imagery. The purpose of this task is to augment events that are present in satellite images with social media reports in order to provide a more comprehensive view. This is of vital importance in context of situational awareness and emergency response for the coordination of rescue efforts.

To align with recent events, the challenge focuses on flooding events, which constitute a special kind of remotely sensed event. The multimedia satellite task is a combination of satellite image processing, social media retrieval and fusion of both modalities. The different challenges are addressed in the following two subtasks. 

* **Disaster Image Retrieval from Social Media [DIRSM]**<br>
The goal of this task is to retrieve all images which show direct evidence of a flooding event from social media streams, independently of a particular event. The objective is to design a system/algorithm that given any collection of multimedia images and their metadata (e.g., YFCC100M, Twitter, Wikipedia, news articles) is able to identify those images that are related to a flooding event. Please note, that only those images which convey an evidence of a flooding event will be considered as True Positives. Specifically, **we define images showing „unexpected high water levels in industrial, residential, commercial and agricultural areas“ as images providing evidence of a flooding event**. The main challenges of this task are the proper discrimination of the water level in different areas (e.g., images showing a lake vs. showing high water at a street) as well as the consideration of different types of flooding events (e.g., coastal flooding, river flooding, pluvial flooding).
<br><p align="center">![alt tag](Preview_DIRSM.png)</p>

* **Flood-Detection in Satellite Images [FDSI]**<br>
The aim of this task is to develop a method/algorithm that is able to identify regions affected by a flooding in satellite images. Participants get image patches of satellite images which cover a wide spatial area for multiple instances of flooding events. The satellite image patches are provided by the organizers of the task and are recorded during (or shortly after) the flooding event. For a list of flooding events at different locations, participants report for given image patches segmentation masks of the flooded area. The percentage of correctly labeled pixels will be evaluated.
<br><p align="center">![alt tag](Preview_FDSI.png)</p>


## What data is provided?

The images and corresponding metadata for the DIRSM task have been extracted from YFCC100M-Dataset. These images are shared under Creative Commons licenses that allow their redistribution. All images are sampled in a way such that there is only one image per user in the dataset. Images will be labeled with the two classes (1) Showing evidence of a flooding event and (2) Showing no evidence of a flooding event. In addition to the images, we will also supply participants with additional metadata information. We will release a development set of 4800 images. Precomputed features will be provided along with the dataset to help teams from different communities to participate to the task.

For the FDSI task, we will provide satellite image patches of flooded regions recorded during (or shortly after) a flooding event. The dataset will contain image patches for different instances of flooding events. The patches have been extracted from high resolution satellite images (3 meter per pixel) gathered from [Planet](https://www.planet.com/) as underlying source of data. For each satellite image patch, there will be one segmentation mask where each pixel contains the class label of background or flooded area.


## How is the performance measured?

The images for the DIRSM task are to be manually annotated with the two class labels (showing evidence/showing no evidence of a flooding event) by human assessors. The correctness of retrieved images will be evaluated with the metric Precision at X (P@X) at various cutoffs, X={50,100, 200, 300, 400, 500}. The metric measures the number of relevant images among the top X results.

The segmentation masks of flooded areas in the satellite images for the FDSI task have been extracted by human assessors. The official evaluation metric of the task is the Percentage of correctly labeled pixels for each submitted satellite image. Therefore, the intersection of the inferred segmentation and the ground truth, divided by the union is computed: ACC = TP/(TP+FN+FP). The evaluation is based on two test-sets: 
* Evaluation on unseen patches which are extracted from the same region as in the dev-set
* Evaluation on unseen patches which are extracted from a new region not being present in the dev-set.


## Who are the task organizers?
* Benjamin Bischke, German Research Center for Artificial Intelligence (DFKI), Germany (first.last at dfki.de)
* Damian Borth, German Research Center for Artificial Intelligence (DFKI), Germany (first.last at dfki.de)
* Christian Schulze, German Research Center for Artificial Intelligence (DFKI), Germany (first.last at dfki.de)
* Venkat Srinivasan, Virginia Tech (Blacksburg VA), US
* Alan Woodley, Queensland University of Technology (QUT), Australia


## Where to get more information?
Detailed information on the task including description of the data, provided features, run submission, etc. can be found on the task wiki.
If you need help or have any questions please contact Benjamin Bischke.
