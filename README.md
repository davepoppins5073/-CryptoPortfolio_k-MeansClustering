# CryptoPortfolio_k-MeansClustering
###  *A novel approach to assembling crypto investment portfolios using k-Means Clustering*

## Requirements/ Installations
The requirement.txt file in this repository contain all the packages you'll need in your conding env. Please make sure to install if you do not have them already. While you could use the package manager [pip](https://pip.pypa.io/en/stable/) to install these individually please make use of the requirement text in the repo.

## The To-Do List:

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


