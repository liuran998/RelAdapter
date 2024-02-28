# Pytorch RelAdapter (Few-shot Link Prediction)

Python 3.6.7
PyTorch 1.0.1
tensorboardX 1.8

## Evironment Setting
This code is lastly tested with:
* Python 3.6.7
* PyTorch 1.0.1
* tensorboardX 1.8

You can also install dependencies by
```bash
pip install -r requirements.txt
```

## Dataset
We provide three datasets: Wiki[^1], FB15K-237[^1] and UMLS.

## Training and Testing

### The format of input training data
### Train/Validation/Test 
* Each line: source_node relation target_node

### Entities & Relations Dictionary
* Each line: ID Name

## Basic Usage
python main.py --dataset <dataset_name> --scoring_function <function_number> --node_embed_size <D> --dimension <D> <br /><br />
### As an example:
The following command trains and validates a DistMult model on umls dataset with 100D in node_embed_size & dimension:<br />
``python main.py --dataset umls 
--scoring_function 1
--node_embed_size 100 
--dimension 100``
<br />The following command trains and validates a RotatE model on umls dataset with 100D (50 Real + 50 Imaginary Dimensions) in node_embed_size & dimension:<br />
``python main.py --dataset umls 
--scoring_function 2
--node_embed_size 50 
--dimension 50``<br />

[^1]: Due to size constraint, Wiki and FB15K-237 has been excluded.
