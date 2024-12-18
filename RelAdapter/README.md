# Pytorch RelAdapter (Few-shot Link Prediction)

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


## Training (UMLS)
```bash
python main.py --seed 1 --step train --metatrain_adaptor False --eval_by_rel False --prefix umlsone_1shot_pretrain --alpha 0.1 --mu 0.3 --neuron 50 --device 0
```

## Test (UMLS)
```bash
python main.py --seed 1 --step test --metatrain_adaptor False --eval_by_rel True --prefix umlsone_1shot_pretrain --alpha 0.1 --mu 0.3 --neuron 50 --device 0
```
**FB15K-237 and UMLS follow the same code format for training and test**

Here are explanations of some important args,

```bash
--dataset:   "the name of dataset, Wiki, FB15K-237, UMLS"
--data_path: "directory of dataset"
--few:       "the number of few in {few}-shot, as well as instance number in support set"
--data_form: "dataset setting, Pre-Train"
--alpha : "the adapter ratio"
--mu : "the context ratio"
--neurons : "the adapter neurons"
--prefix:    "given name of current experiment"
--device:    "the GPU number"
```
[^1]: Due to size constraint, Wiki and FB15K-237 have been excluded.
