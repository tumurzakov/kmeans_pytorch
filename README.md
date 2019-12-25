# K Means using PyTorch
PyTorch implementation of kmeans for utilizing GPU

# Getting Started
```

import torch
import numpy as np
from kmeans_pytorch import kmeans, kmeans_predict

# data
data_size, dims, num_clusters = 1000, 2, 3
x = np.random.randn(data_size, dims) / 6
x = torch.from_numpy(x)

# kmeans
cluster_ids_x, cluster_centers = kmeans(
    X=x, num_clusters=num_clusters, distance='euclidean', device=torch.device('cuda:0')
)
```

see `example.ipynb` for more elaborate example

# Requirments
* [PyTorch](http://pytorch.org/) version >= 1.0.0
* Python version >= 3.6

# Installation

install with `pip`:
```
pip install fairseq
```

**Installing from source**

To install from source and develop locally:
```
git clone https://github.com/subhadarship/kmeans_pytorch
cd kmeans_pytorch
pip install --editable .
```

# Notes
- useful when clustering large number of samples
- utilizes GPU for faster matrix computations
- support euclidean and cosine distances (for now)
