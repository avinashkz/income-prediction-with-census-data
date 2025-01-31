## Data Set

[Adult Data Set](http://archive.ics.uci.edu/ml/datasets/Adult) from UCI Machine Learning Repository. Also known as "Census Income" dataset. It is used to predict whether a person's income exceeds $50K/yr based on census data.

| Dataset Features           |                      |
|----------------------------|----------------------|
| Number of Records:         | 488442               |
| Number of Variables:       | 14                   |
| Attribute Characteristics: | Categorical, Integer |
| Missing Values:            | Yes                  |
| Associated Tasks:          | Classification       |
| Date Collected:            | 1996-05-01           |


## Introduction

For this project I will be using some Feature Selection techniques and develop a model that can correctly classify the  `salary-class`(greater than or less than $50k) a person. The features of each person provided in the dataset are `age`, `workclass`, `final-weight`, `education`, `education-number`, `marital-status`, `occupation`, `relationship`, `race`, `sex`, `capital-gain`, `capital-loss`, `hours-per-week` and `native-country` ?

## Plan of Action

Create a script to read the data from the UCI Machine Learning Repository and store the data locally in the data folder for processing the data before it is used.

Read the data into a new script to wrangle the data to use data visualization for better understand the dataset and how the different variables are distributed. Also, identify the variables that can better explain the problem.

Split the categorical variables into multiple variables so that these variables can be used in a classification algorithm. Then, select a classification machine learning algorithm and train it on the test data and then predict the `salary-class` of all the people in test dataset to evaluate the model's performance. Now, try tuning the hyper-parameters to improve the model's performance. If the results applied using the algorithm is not satisfactory then apply different supervised classification algorithms to check if the algorithm is most accurate in classifying the data.

## Summary

The project aims to classify people into two groups, i.e. who earn **more than $50,000** and **less than $50,000**. People are classified based on features such as `age`, `workclass`, `education`, `marital-status`, `occupation`, `race`, `sex`, `hours-per-week` and `native-country`.

## How to Run Data Analysis

The scripts should be run in the order specified below. All the arguments are specified with default values. If required, all the arguments that are read in by the scripts are specified below. By default, the raw data are in the data folder, and the processed data and images will be stored in the doc folder. The rendered documents are stored in the results folder. These can be modified using the arguments for the scripts.

### Run Scripts Individually

1. Rscript data_read.R --train=train_url --test=test_url

2. Rscript data_processing.R --write=write_folder

3. Rscript data_summary.R --read=read_path --write=write_path

4. Rscript data_viz.R --read=read_path --write=write_path

5. python3 model.py

6. Rscript -e 'rmarkdown::render("src/report.Rmd", output_dir = "results")'

### Run Scripts using Makefile

*make all* -> For running all the files.

*make clean* -> To delete all the files created.

### How to Run Project in Docker

Link to Docker Repo : [income-prediction-with-census-data](https://hub.docker.com/r/avinashkz/income-prediction-with-census-data/)

Run the following commands in terminal in the given order:

1. Docker Pull Command : *docker pull avinashkz/income-prediction-with-census-data*

2. *docker run --rm -it -v < repo local path >:/home/income-prediction avinashkz/income-prediction-with-census-data /bin/bash*

3. *cd home/income-prediction*

4. *make all*

5. *make clean* -> To delete all the files created

### Run using *Packrat* and *conda env*

1. Open *income-prediction.Rproj*.

2. packrat::restore()

3. conda env create -f environment.yml

4. source activate income

5. *make all*

6. *make clean* -> To delete all the files created


## Software Dependencies

### R

1. Tidyverse
2. Optparse

### Python

1. Numpy
2. Pandas
3. Matplotlib
4. Scikit Learn

## Report

The report for the mini project can be viewed at [Report.md](results/report.md).
