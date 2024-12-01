
# TargetDiff (Using for test VFDiff results)



The code is borrowed from TargetDiff [[PDF]](https://openreview.net/pdf?id=kJqXEPXMsE0)  using for test VFDiff results. 

This project is intended for reviewers to test during the review period.

We have added the `targetdiff/evaluate_diffusion.py` file, which is identical to `targetdiff/scripts/evaluate_diffusion.py` in terms of bond JSD evaluation. 

Additionally, we have provided the log files generated after running the evaluation. 

We plan to release our model code publicly after the paper is accepted.

<p align="center">
  <img src="assets/overview.png" /> 
</p>

## Installation

### Dependency

The code has been tested in the following environment:


| Package           | Version   |
|-------------------|-----------|
| Python            | 3.8       |
| PyTorch           | 1.13.1    |
| CUDA              | 11.6      |
| PyTorch Geometric | 2.2.0     |
| RDKit             | 2022.03.2 |

### Install via Conda and Pip
```bash
conda create -n targetdiff python=3.8
conda activate targetdiff
conda install pytorch pytorch-cuda=11.6 -c pytorch -c nvidia
conda install pyg -c pyg
conda install rdkit openbabel tensorboard pyyaml easydict python-lmdb -c conda-forge

# For Vina Docking
pip install meeko==0.1.dev3 scipy pdb2pqr vina==1.2.2 
python -m pip install git+https://github.com/Valdes-Tresanco-MS/AutoDockTools_py3
```
The code should work with PyTorch >= 1.9.0 and PyG >= 2.0. You can change the package version according to your need.


### Test for VFDiff results
```bash
unzip targetdiff.zip
```
Please move metrics_-1.pt in **Supplementary Materials** to 
```bash
./targetdiff/
```
run the evaluation file
```bash
cd targetdiff
python evaluate_diffusion.py
```
