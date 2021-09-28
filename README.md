# PairRE 

Code for paper [**PairRE: Knowledge Graph Embeddings via Paired Relation Vectors**](https://arxiv.org/abs/2011.03798).

This implementation of PairRE for [**Open Graph Benchmak**](https://arxiv.org/abs/2005.00687) datasets (ogbl-wikikg and ogbl-biokg) is based on [**OGB**](https://github.com/snap-stanford/ogb). Thanks for their contributions.


## Setup

To run the code, you need the following dependencies:

- [Pytorch 1.4.0](https://pytorch.org/)
- [ogb 1.2.2](https://github.com/snap-stanford/ogb) for wikikg
- [ogb 1.2.4](https://github.com/snap-stanford/ogb) for wikikg2

## Results

The results of **PairRE** on **ogbl-wikikg**, **ogbl-biokg** and **ogbl-wikikg2** are as follows.
 
### ogbl-wikikg
| | #Dim | #Parameters | Hardware| Test MRR | Valid MRR |
|:------:|:------:|:------:|:------:|:--------:|:--------:|
| PairRE | 100 | 250,167,400 | 16GB GPU | 0.4912 ± 0.004 | 0.5013 ± 0.004 | 
| PairRE | 200 | 500,334,800 | 16GB GPU | 0.5289 ± 0.003 | 0.5529 ± 0.001 | 

### ogbl-biokg
| | #Dim | #Parameters | Hardware| Test MRR | Valid MRR |
|:----------:|:----------:|:----------:|:----------:|:----------:|:----------:|
| PairRE | 2000 | 187,750,000 | 16GB GPU | 0.8164 ± 0.0005 | 0.8172 ± 0.0005 | 

### ogbl-wikikg2
| | #Dim | #Parameters | Hardware| Test MRR | Valid MRR |
|:------:|:------:|:------:|:------:|:--------:|:--------:|
| PairRE | 100 | 250,167,400 | 16GB GPU | 0.4849 ± 0.003 | 0.4941 ± 0.004 | 
| PairRE | 200 | 500,334,800 | 16GB GPU | 0.5208 ± 0.003 | 0.5423 ± 0.002 | 

## Running the code 

### ogbl-wikikg

```bash
cd wikikg && sh examples.sh

```
### ogbl-biokg
```bash
cd biokg && sh examples.sh
```

### ogbl-wikikg2
Please update ogb package to version 1.2.4. 
The hyperparameters are same to the experiments in ogbl-wikikg.

```bash
cd wikikg && sh examples.sh
```

The details of the optional hyperparameters can be found in examples.sh.


# PairRE for FB15k, FB15k-237, DB100k
These experiments are based on this [**repository**](https://github.com/DeepGraphLearning/KnowledgeGraphEmbedding). We add the [**score function**](https://github.com/alipay/KnowledgeGraphEmbeddingsViaPairedRelationVectors_PairRE/blob/main/biokg/model.py#L232-L240) of PairRE to this repository directly.

Commands to reproduce the reuslts are:

FB15k-237
```bash
bash run.sh train PairRE FB15k-237 0 0 1024 256 1500 6.0 1.0 0.00005 100000 16 -dr
```

FB15k: 
```bash
bash run.sh train PairRE FB15k 0 0 1024 256 1500 15.0 1.0 0.0001 150000 16 -dr
```

DB100k: 
```bash
bash run.sh train PairRE DB100K 0 0 1024 256 500 9.0 1.0 0.00005 150000 16 -dr'
```

