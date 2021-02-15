
# Feature Matching Using Computer Vision
## Matching Similar Objects

**Author**: Miguel Santana

Thank you for reviewing this repository. The author's contact info, sources and social media profiles are listed below under **further information.**

The contents of this repository detail an analysis of images and matching similar objects of different sizes and orientations using ratio tests, brute force matching with orb descriptors, SIFT descriptors and a FLANN based matcher. 

### The Data

The images are originally sourced from Udemy. The Udemy citation is available below under **sources.** 

### Import Data
The data includes two images: the first being an image of a cereal box and the second being an image of a cereal isle in a grocery store. 

**Image 1: Object to Match**

![png](/images/reeses_puffs.png)


**Image 1: Imported In Gray Scale**

![png](/images/reesesgray.png)


**Image 2: Matching Features From Image 1 Onto Image 2**

![png](/images/many_cereals.png)


**Image 2: Imported In Gray Scale**

![png](/images/cerealgray.png)


Note: The image is in the lower left hand corner but it is important to note that the images are different sizes and do vary overall with image 1 illustrating "Family Size" on top of the box.


# Forms of Feature Matching (3)
## 1) Brute Force Detection with ORB Descriptors

Process: 
* initiate ORB object
* find key points and descriptors
* create brute force matcher object
* match descriptors
* sort matches based on distance
    * smaller distances = better matches
* draw the top 25 matches


**Brute-Force Detection | ORB Descriptors | Feature Matching**

![png](/images/BFD_ORB.png)


Looks like Brute Force Detection with ORB Descriptors didn't do a very good job in this case. It's worth noting this type of detector struggles with matching features of different sizes. Next, we will try two other options for matching. 


## 2) Brute Force Matching with SIFT Descriptors and a Ratio Test
#### SIFT | Scale Invariant Feature Transform

Process: 
* create SIFT object
* find key points and descriptors
* create brute force matcher object
* match descriptors
* apply a ratio test to narrow down best matches
* draw top matches


**Brute-Force Detection | SIFT Descriptors & Ratio Test | Feature Matching**

![png](/images/BFM_SIFT.png)


## 3) FLANN based Feature Matching
#### FLANN | Fast Library for Approximate Nearest Neighbors

Process: 
* create SIFT object
* find key points and descriptors
* FLANN parameters / dictionary
* match descriptors
* apply a ratio test to narrow down best matches
* draw top matches


**FLANN based Feature Matching**

![png](/images/FLANN.png)


# Interpreting Results | Recommendations | Used Cases

The SIFT and FLANN algorithms performed the best in this particular case. The brute force detection with ORB descriptors struggled due to the variance in size between objects and as a result - features that needed to be matched.

Feature matching is extremely popular in image detection, facial recognition and even inventory related business tasks. As OpenCV and Computer Vision continue to develop, image detection will continue to grow and integrate with business as the vast amounts of data available on social media or collected by corporations become more useful in connecting with consumers. There are both positive and negative sentiments to this type of analysis. As the tools continue to develop we will understand more about potential use cases and their relationships to ethics in business. 

### Limitations, Future Work

#### Limitations
Many of the tools in OpenCV and Computer Vision are still being developed with docstrings not being available (as is the case for brute force matcher object used above). 

#### Future Work

Future projects will include similar themes within the context of video and how feature matching relates to non static images. 

### Further Information
Please review the narrative of our analysis in [our jupyter notebook](./jupyter_notebook.ipynb) or review our [presentation](/powerpoint/powerpoint.pdf)

For any additional questions, please reach out via email at santana2.miguel@gmail.com, on [LinkedIn](https://www.linkedin.com/in/miguel-angel-santana-ii-mba-51467276/) or on [Twitter.](https://twitter.com/msantana_ds)

#### Sources

Additional analysis, notes and file sources can be found on Udemy's website. 

* Course Name: Python for Computer vision with OpenCV and Deep Learning by Jose Portilla.

##### Repository Structure:

```

├── README.md               <- The top-level README for reviewers of this project.
├── jupyter_notebook.ipynb     <- narrative documentation of analysis in jupyter notebook
├── presentation.pdf        <- pdf version of project presentation

```
