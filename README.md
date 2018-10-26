# Ternary Semiconductors from Machine Learning and Crystal Structure Prediction

This repository contains scripts and datasets needed to reproduce the machine learning results from a recent paper by Amsler et al. 

## Contents

The key machine learning task performed in this manuscript is to identify the compositions in the Ba-As-S ternary system that are favorable for semiconductor applications.

The `make-deltae-model.in` and `make-bandgap-model.in` models employ [Magpie](https://bitbucket.org/wolverton/magpie) to train machine learning models on data from the [OQMD](http://oqmd.org/) to predict stability (via the formation energy) and the band gap energy fo the model. The training set for the model is available in [`./datasets/`](./datasets/) and the models are in [`./models/`](./models) directory. 

The `scan-BaAs-system.in` script runs the models on the Ba-As-S system and computes the stability of each prediction with respect to the convex hull of the training set. 

The Jupyter notebook `plot-BaAsS-results.ipynb` produces the plots seen in the paper.

## Installation

You must clone the repository using `git clone --recursive` to get the necessary Magpie source code. Then, follow the instructions in the Magpie documentation to compile Magpie.

Besides Magpie, you need to install a Python 3 version of Jupyter with the packages listed in `requirements.txt`

## Running the Scripts

Call `./run-all.bs` to execute all of the scripts in this study.
