

# Interpretable multiclass classification by MDL-based rule lists
This repository contains the code for all the experiments in Chapter 3 and of the paper  [Interpretable multiclass classification by MDL-based rule lists. Hugo M. Proença, Matthijs van Leeuwen. (2019) ](https://arxiv.org/abs/1905.00328).

NOTE: this code is outdated but it was inserted here for reproducibility reasons, thus, for the most recent version of the code for Predictive Rule Lists please refer to [https://github.com/HMProenca/RuleList](https://github.com/HMProenca/RuleList).
.



## Citation

In a machine learning (prediction) context for problems of classification, regression, multi-label classification, multi-category classification, or multivariate regression cite the corresponding bibtex of the first classification application of MDL rule lists:


in the context of data mining and subgroup discovery please refer to subgroup lists:

```
@article{proencca2021robust,
  title={Robust subgroup discovery},
  author={Proen{\c{c}}a, Hugo Manuel and B{\"a}ck, Thomas and van Leeuwen, Matthijs},
  journal={arXiv preprint arXiv:2103.13686},
  year={2021}
}
```

## Licenses

MIT License

## Contact

If there are any questions or issues, please contact me by mail at `hugo.manuel.proenca@gmail.com` or open an issue here on Github.



# Related Work #
 * [Discovering outstanding subgroup lists for numeric targets using MDL. Hugo M. Proença, Peter Grünwald, Thomas Bäck, Matthijs van Leeuwen. ECML-PKDD(2020): ](https://arxiv.org/abs/2006.09186) -- experiments code available [here](https://github.com/HMProenca/SSDpp-numeric)
 * [Robust subgroup discovery. Hugo M. Proença,Thomas Bäck, Matthijs van Leeuwen. (2021) ](https://arxiv.org/abs/2103.13686) -- experiments code available [here](https://github.com/HMProenca/RobustSubgroupDiscovery)

# To run this code 

This code  requires the external frequent itemset mining package "PyFIM," available at [http://www.borgelt.net/pyfim.html).

To replicate the experiments in Chapter 3 and on the paper please run:
```python
mdl_rulelists.py
```

for a simple example using this version of the code:

```python
 import mdl_rulelists as mdlrl
 filename = "./datasetexample/breast.csv" 
 minsupp = 5 # it is a 5% minimum support threshold
maxlen = 4
data_it, cl,item2class = mdlrl.binary2itemsets(filename) 
data_train, data_test = divide "data_it" according to your intereststs
modelprob,modelraw,lfinal,lorig,nfreqp = mdlrl.mdl_rulelist(data_train, cl,minsupp,maxlen)
pred, probvector, probmatrix,RULEactivated = mdlrl.prediction(data_test,modelprob,cl,item2class)
#in case a prediction needs to be done one can use mdlrl.prediction
#where "datatest" is a dataset without class labels 
#(it is actually indiferent if it has class labels or not)
```
