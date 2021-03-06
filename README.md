The Anomalous-Vertices-Detection project is a Python package for performing graph analysis.
The package supports extracting graphs'  topological features, performing link prediction, and identifying anomalous vertices.
The package supports various graph packages ([NetworkX](https://networkx.github.io), [SGraph](https://turi.com/products/create/docs/generated/graphlab.SGraph.html), [iGraph](http://igraph.org/python/), and
[GraphTools](https://graph-tool.skewed.de/)) and Machine Learning packages ([SciKit](http://scikit-learn.org/) and [GraphLab](https://turi.com/products/create/docs/index.html)).
This project is under development and has a many planned improvements. More details on the project can be find in the our paper titled ["Unsupervised Anomalous Vertices Detection Utilizing Link Prediction Algorithms"](https://arxiv.org/abs/1610.07525) and in the NetSciX 2017 [presentation](http://slides.com/dimakagan/netscix).


## Installation
```
git clone git://github.com/Kagandi/anomalous-vertices-detection.git
pip install -r requirements.txt
For Windows I suggest using conda and running:  run: conda env create -f environment.yml
The default installation only installs networkx and scikit-learn.
It is also possible to use the package with igraph, SGraph, GraphLab and GraphTools.
Note: Currently the package works best with networkx + scikit-learn or networkx + GraphLab.
```
## Usage
Init:
```python
from anomalous_vertices_detection.configs.graph_config import GraphConfig
from anomalous_vertices_detection.graph_learning_controller import *
from anomalous_vertices_detection.graphs.graph_factory import GraphFactory
from anomalous_vertices_detection.learners.gllearner import GlLearner

labels = {"neg": "Real", "pos": "Fake"}
dataset_config = GraphConfig("my_dataset", my_dataset_path, is_directed=True)
gl = GraphLearningController(GlLearner(labels=labels), dataset_config)
my_graph = GraphFactory().make_graph_with_fake_profiles(dataset_config.data_path,
                                            is_directed=dataset_config.is_directed,
                                            pos_label=labels["pos"], neg_label=labels["neg"])
```

## Todo
- [ ] Migrate to networkx 2.0
- [ ] Complete the documentation
- [X] Write Jupiter notebooks
- [ ] Clean the code
- [X] Add setup.py
- [X] Add requirements.txt
- [X] Add basic examples
- [X] Add more examples
- [ ] Add more test
- [ ] Python 3.6 support
- [ ] Migrate form unittest to pytest


