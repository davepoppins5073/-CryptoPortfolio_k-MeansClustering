# CryptoPortfolio_k-MeansClustering
Clustering cryptocurrencies by their performance over different periods. Visual displays of the findings.


## Requirements/ Installations
The requirement.txt file in this repository contain all the packages you'll need in your conding env. Please make sure to install if you do not have them already. While you could use the package manager [pip](https://pip.pypa.io/en/stable/) to install these individually please make use of the requirement text in the repo.

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
