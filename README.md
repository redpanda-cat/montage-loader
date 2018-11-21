# Montage

[Montage](https://github.com/shahcompbio/montage) is a web-based visualization platform, featuring several interactive dashboards of single cell genomics data.

This repo holds the python scripts in order to load into our [Elasticsearch](https://www.elastic.co/) backend.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

- ElasticSearch
- Python 2.7
- pip
- virtualenv

### Installing

Extract the ElasticSearch archive, and install the mapper-size plugin

```
./bin/elasticsearch-plugin install mapper-size
```

Then start the ElasticSearch instance

```
./bin/elasticsearch
```

### Loading Data

Create a Python virtualenv and install the required packages

```
virtualenv ~/pythonenv
source ~/pythonenv/bin/activate
pip install -r pip-requires.txt
```

Load using the appropriate dashboard loader with the correct YAML file. For example:

```
python tree_cellscape_loader.py -y directory/to/yaml/data_metadata.yaml
```

This will load an entry into the Analysis index, as well as the appropriate data files. You can view the [README in /loader](./loader/common/README.md) to see more information about the data types.
