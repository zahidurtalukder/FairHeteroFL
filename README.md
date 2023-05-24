

# FairHeteroFL: Hardware-Sensitive Fairness in Federated Learning with Heterogeneous Environment

This repository is the official implementation of FairHeteroFL-
<p align="center" width="100%">
    <img width="66%" src="images/Architecture.jpg">
</p>

>📋 we propose a novel hardware-sensitive FL method called FairHeteroFL that promotes fairness among heterogeneous federated clients. Our approach offers tunable fairness within a group of devices with the same ML architecture as well as across different groups. Our evaluation under MNIST, FEMNIST, CIFAR10, and SHAKESPEARE datasets reveals that FairHeteroFL can reduce variance among participating clients’ test loss compared to the existing state-of-the-art techniques, resulting in increased overall performances

## Requirements

To install requirements:

```setup
pip install -r requirements.txt
```
>📋  Getting Dataset Directly

- You can directly download the Dataset for MNIST [MNIST IID](https://drive.google.com/file/d/1KWLSAWqeChXsKWoufc85gQ8xaG6ocUWt/view?usp=sharing), [MNIST Non-IID](https://drive.google.com/file/d/1oOcLdDUq7dAvWMWTAO9j0-ddBEesS9hh/view?usp=sharing), [MNIST Non-IID Extreme](https://drive.google.com/file/d/1ty8wQOHasDtAW1lQilI_bvq_BfbSJIPK/view?usp=sharing).
- You can directly download the Dataset for CIFAR10 [CIFAR10 IID](https://drive.google.com/file/d/1vw-axxdsMDsczZAab7LO6PC8_Av4jr_g/view?usp=sharing), [CIFAR10 Non-IID](https://drive.google.com/file/d/1qRlxFQrNV_ksCavDAoW8_cMFkDAnA4hr/view?usp=sharing), [CIFAR10 Non-IID Extreme](https://drive.google.com/file/d/1qRlxFQrNV_ksCavDAoW8_cMFkDAnA4hr/view?usp=sharing).
- You can directly download the Dataset for FEMNIST [FEMNIST TRAIN](https://drive.google.com/file/d/1dhwHcwHvgHGraG-OMXzVA4WrpiNLoqAV/view?usp=sharing), [FEMNIST TEST](https://drive.google.com/file/d/1Oe3yEPa2TruLkEOTLsZtipZjERBs-a1M/view?usp=sharing)

Keep the dataset in the same directory of the dataset name.

## Training

To train the model(s) in the paper, navigate to the directory and run this command:

MNIST IID train
```
python train mnist iid.py q qm1 qm2 qm3 qm4 qm5
```
MNIST Non-IID train
```
python train mnist noniid.py q qm1 qm2 qm3 qm4 qm5
```
MNIST Non-IID Extreme train
```
python train mnist noniid extreme.py q qm1 qm2 qm3 qm4 qm5
```
CIFAR10 IID train
```
python train cifar iid.py q qm1 qm2 qm3 qm4 qm5
```
CIFAR10 Non-IID train
```
python train cifar noniid.py q qm1 qm2 qm3 qm4 qm5
```
CIFAR10 Non-IID Extreme train
```
python train cifar noniid extreme.py q qm1 qm2 qm3 qm4 qm5
```
FEMNIST train
```
python train femnist.py q qm1 qm2 qm3 qm4 qm5
```
SHAKESPEARE train
```
python train shakespeare.py q qm1 qm2 qm3 qm4 qm5
```

>📋  This train the model with particualar value of q and qms. After training the train and test losses and accuracies are automatically save in the data folder for future evaluation. You can tune q and qms value to get your desired model performance.

## Evaluation

To evaluate the groupwise performance, run the evaluate.py located in data for every dataset:

```eval
python evaluate.py "file_name"
```

>📋  The file name should include extension ".pkl". This produces the groupwise mean and variance of the test loss for a particular value of q and qms.
## Pre-trained Models

You can download pretrained models here:

- [MNIST](Mnist/pretrain%20model) trained on HeteroFL and FairHeteroFL can be found here. 
- [CIFAR10](https://github.com/Zahid2734/FairHeteroFL/tree/main/Cifar10/pretrain%20model) trained on HeteroFL and FairHeteroFL can be found here. 
- [FEMNIST](https://github.com/Zahid2734/FairHeteroFL/tree/main/Femnist/pretrain%20model) trained on HeteroFL and FairHeteroFL can be found here.
- [SHAKESPEARE](https://github.com/Zahid2734/FairHeteroFL/tree/main/Shakespeare/pretrain%20model) trained on HeteroFL and FairHeteroFL can be found here.

>📋 The pretrained model were the model used to generate the main result in the paper. You also can generate the model using the parameter of q and qms in the paper.

## Results

Our model achieves the following performance on :
<p align="center" width="100%">
    <img width="80%" src="images/result.PNG">
</p>

>📋  This is the main result of our paper. This shows that with proper tuning of q and qms, we can get more balanced performance accross clients from all the groups with different hardware capabilities. 


## Contributing

>📋  Pick a licence and describe how to contribute to your code repository. 
