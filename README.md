
# Blancing Principle for Domain Adaptation

## Abstract

We address the unsolved algorithm design problem of choosing a justified regularization parameter in unsupervised domain adaptation. This problem is intriguing as no labels are available in the target domain. Our approach starts with the observation that the widely-used approach of minimizing the source error, weighted by a distance measure between source and target feature representations, shares characteristics with regularized ill-posed inverse problems.
Regularization parameters in inverse problems can be chosen by the fundamental \textit{principle of balancing} approximation and sampling errors. We use this principle to balance learning errors and domain distance in a target error bound. As a result, we obtain a theoretically justified rule for the choice of the regularization parameter. In contrast to the state of the art, our approach allows source and target distributions with disjoint supports. An empirical comparative study on benchmark datasets underpins the performance of our approach.

## Installing

1. Clone repository

```bash
git clone <our-repo-link>
cd bpda-1D3D
```


2. Create a python 3 conda environment
```bash
conda env create -f environment.yml
```

3. Install package
```bash
pip install -e .
```

4. Ensure that all required temp directories are available

  * `tmp`
  * `runs`
  * `data`

## Compute Results

1. Train domain adaptation method by calling:

```bash
CUDA_VISIBLE_DEVICES=<device-id> PYTHONPATH=. python scripts/train.py --config configs/<your-config>.json
```

2. Evaluate results

Set the respective `base_dir` and `method` setting in the `viz/results_extractor_MiniDomainNet.py` file and run:

```bash
PYTHONPATH=. python viz/results_extractor_MiniDomainNet.py
```

## References

* [Moment Matching for Multi-Source Domain Adaptation](http://ai.bu.edu/M3SDA/)
* [Amazon product data](https://jmcauley.ucsd.edu/data/amazon/)
* [Unsupervised Domain Adaptation by Backpropagation](https://github.com/fungtion/DANN)
* [Towards Accurate Model Selection in Deep Unsupervised Domain Adaptation](https://github.com/thuml/Deep-Embedded-Validation)