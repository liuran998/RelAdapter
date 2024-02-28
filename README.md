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

We use the few-shot variants of Wiki, FB15K-237 and UMLS to test our model. You can download the zip files where we put the datasets and pretrain embeddings together from [Dropbox](https://www.dropbox.com/scl/fi/x7eih477f0gsx7lo0dksi/Dataset.zip?rlkey=gu2lcy1532u2ldux1opq2izad&dl=0). 

## Training

```bash
python main.py --seed 1 --step train --metatrain_adaptor False --eval_by_rel False --prefix wikione_1shot_pretrain --alpha 0.3 --mu 0.05 --neurons 50 --device 0
```

## Test
```bash
python main.py --seed 1 --step test --metatrain_adaptor False --eval_by_rel True --prefix wikione_1shot_pretrain --alpha 0.3 --mu 0.05 --neurons 50 --device 0
```

Here are explanations of some important args,

```bash
--dataset:   "the name of dataset, Wiki, FB15K-237, UMLS"
--data_path: "directory of dataset"
--few:       "the number of few in {few}-shot, as well as instance number in support set"
--data_form: "dataset setting, Pre-Train or In-Train"
--alpha : "the adapter transformation coefficient"
--mu : "the contextual coefficient"
--neurons : "the number of hidden neurons in adapter"
--prefix:    "given name of current experiment"
--device:    "the GPU number"
```

[^1]: Due to size constraint, Wiki and FB15K-237 has been excluded.
