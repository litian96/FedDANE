# FedDANE: A Federated Newton-Type Method

This repository contains the code and experiments for the paper:

> [FedDANE: A Federated Newton-Type Method](https://arxiv.org/abs/2001.01920)
> 
> Asilomar Conference on Signals, Systems, and Computers 2019 (Invited Paper)

FedDANE is an optimization method that we adapt from DANE, a method for classical distributed optimization, to handle the practical constraints of federated learning. We provide convergence guarantees for this method when learning over both convex and non-convex functions. Despite encouraging theoretical results, we find that the method has underwhelming performance empirically. We identify low device participation and statistical device heterogeneity as two underlying causes of this underwhelming performance. In the paper, we also suggest several directions of future work.


This repository contains a set of empirical evaluation on both synthetic and real-world datasets. FedDANE consistently underperforms baselines of FedAvg and FedProx in realistic federated settings. 


## Usage

The usage is almost the same as that of the [FedProx](https://github.com/litian96/FedProx) code, except that we are using a different optimizer specified in `flearn/optimizer/pggd.py`. For example, command lines to reproduce the results on the synthetic IID data are:


```
mkdir log_synthetic
bash run_trainer.sh synthetic_iid fedavg 0 | tee log_synthetic/iid_fedavg_c10_e20
bash run_trainer.sh synthetic_iid fedprox 1 | tee log_synthetic/iid_fedprox_c10_e20
bash run_trainer.sh synthetic_iid feddane 0 | tee log_synthetic/iid_feddane_c10_e20
python plot.py
```


## References
See our [FedDANE](https://arxiv.org/abs/2001.01920) paper for more details as well as all references.
