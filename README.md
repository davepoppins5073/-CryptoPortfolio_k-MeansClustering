# CryptoPortfolio_k-MeansClustering
###  *A novel approach to assembling crypto investment portfolios using k-Means Clustering*

## Requirements/ Installations
The requirement.txt file in this repository contain all the packages you'll need in your conding env. Please make sure to install if you do not have them already. While you could use the package manager [pip](https://pip.pypa.io/en/stable/) to install these individually please make use of the requirement text in the repo.

## The To-Do List:
The sections below follow the parts of my ipynb for this project.

* <b>Section 1:</b> Import the Data
* <b>Section 2:</b> Prepare the Data 
* <b>Section 3:</b> Find the Best Value for `k` Using the Original Data
* <b>Section 4:</b> Cluster Cryptocurrencies with K-means Using the Original Data
* <b>Section 5:</b> Optimize Clusters with Principal Component Analysis
* <b>Section 6:</b> Find the Best Value for `k` Using the PCA Data
* <b>Section 7:</b> Cluster the Cryptocurrencies with K-means Using the PCA Data
* <b>Section 8:</b> Visualize and Compare the Results

---

### pip install for Requirements
```bash
python -m pip install -r requirements_10.txt
```
### Imports
```python
# Import the required libraries and dependencies
import pandas as pd
import numpy as np
import hvplot.pandas
from path import Path
from sklearn.cluster import KMeans
from sklearn.decomposition import PCA
from sklearn.preprocessing import StandardScaler
```
Note on Imports: 
I included the following code snippet in the ipynb because it makes use of the kneed library to programmatically find `k`. This is extrat supplemental data and as such doesnt have to be part of your imports if you choose to do thiss as well.

<mark><b>Code Snippet</mark></b>
```
from kneed import KneeLocator

kl = KneeLocator(
    k, 
    inertia, 
    curve="convex", 
    direction="decreasing"
)
elbow=kl.elbow
print('Elbow = {}'.format(elbow))

```
## Discussions

**Image 1:**
<img width="787" alt="Screen Shot 2022-05-29 at 11 04 07 PM" src="https://user-images.githubusercontent.com/101449950/170910567-16d86352-f00e-4963-83bd-15ab236fbaf4.png">


**Image 2:**
<img width="1444" alt="Screen Shot 2022-05-29 at 11 11 58 PM" src="https://user-images.githubusercontent.com/101449950/170910581-4f07f163-047a-4414-8856-f0433ea22e48.png">

There are some benefits that come with using fewer features for K-Means:
1.  I noticed that the the y-intercept for the pca elbow curve was less than that for the elbow curve done with the original data. I would imagine that the the y-intercept value of the curve is equal to the yinitial. So the less components we have the less the magnitude of the initial inertia. If inertia "measures how well a dataset was clustered by K-Means, then I would imagine the greater the inertia, the less a dataset can be clustered by K means. To quote the source listed below, 'a good model is one with low inertia AND a low number of clusters (k). 
**SOURCE:**
<a href="https://www.codecademy.com/learn/machine-learning/modules/dspath-clustering/cheatsheet#:~:text=K%2DMeans%3A%20Inertia,number%20of%20clusters%20(%20K%20)">K means Clustering</a>

2. There seemed to be much less outliers. Looking at the second clustering graph, the x-axis goes from -1 to 8. It doesnt take into considering the 3 data points we had after -1 on the x-axis. In my opinion  not having to deal with the totality of the dataset and ignoring some outliers helped to have a cleaner graph.

I was able to find the following resource that reiterates my point about reducing noise:

"PCA eliminates those low variance dimension (noise), so itself adds value (and form a sense similar to clustering) by focusing on those key dimension In simple terms, it is just like X-Y axis is what help us master any abstract mathematical concept but in a more advance manner."
**SOURCE:**
<a href="https://stats.stackexchange.com/questions/183236/what-is-the-relation-between-k-means-clustering-and-pca"> K-mean and PCA </a>


## Sources
This study was quoted in many places online talking about how to use PCA with K means clustering.  It was prtty informative but a lot went over my head,however from what I was able to glean i thought to share here as a source. 
<img width="787" alt="Screen Shot 2022-05-29 at 11 04 07 PM" src="https://user-images.githubusercontent.com/101449950/170909820-ba57f132-0efe-45d8-bda7-8af13dd5c707.png">


