# mrs_spring_tutorial
This repo contains data files and code used for tutorial MD00 at the MRS spring meeting 2023.

Project 1: perovs_dft_ml

This project uses high-throughput density functional theory (DFT) data on halide perovskite alloys to train predictive machine learning (ML) models using a variety of regression algorithms for properties of interest and perform multi-objective inverse design using genetic algorithm (GA).

DFT calculations are performed at two levels of theory: GGA-PBE (referred to as PBE henceforth) and HSE06 (referred to as HSE henceforth), resulting in a total dataset of ~ 800 points. We further have around 100 data points from experiments, collected from the literature. All data is read using the different .csv files. Three properties are computed: the decomposition energy (in eV per formula unit), the band gap (in eV), and the spectroscopic limited maximum efficiency (SLME, in fraction, indicating a theoretical limit for photovoltaic power conversion efficiency). Every data point or compound is identified using an Index and a Formula. Two types of input descriptors are defined (to be used for training input -> output predictive models): a composition vector (14 dim) and a elemental properties vector (36 dim). In addition, one-hot encoded vectors are used with both to identify perovskite phase (cubic, tetragonal, orthrhombic, or hexagonal) and data fidelity (PBE, HSE, or Expt). The data is split into 4 types: PBE only, HSE only, PBE+HSE, and PBE+HSE+expt.

The Jupyter notebook "DFT-ML.ipynb" calls relevant python packages, reads the DFT and/or experimental data, performs some data visualization, and then has different sections for a variety of ML treatments including coefficients of linear correlation between descriptors and properties, elasticnet regression, random forest regression, kernel ridge regression, and genetic algorithm.


This repo also contains Jupyter notebooks on Gaussian Process regression, Active Learning, Neural Network regression (with a demonstration on the perovskite dataset), and Convolutional Neural Networks. All these notebooks will be part of the tutorial.
