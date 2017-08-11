---
title: "Intro to Data Science"
date: 2017-09-08T03:17:08-07:00
draft: false
category: lab
---

# Lab 1: Intro to Data Science

Due: 9/8/2017

## Setting up your computer

### Install Python3

We recommend the following methods:

* [Linux](http://python-guide-pt-br.readthedocs.io/en/latest/starting/install3/linux/)
* [Mac OS X](http://python-guide-pt-br.readthedocs.io/en/latest/starting/install3/osx/)
* [Windows](http://python-guide-pt-br.readthedocs.io/en/latest/starting/install3/win/)

It is fine if you already have a different version of Python 3 installed. However, you
may run into errors that we have not yet come across.

### Downloading the lab files.

#### Git
```git clone https://github.com/data1030/...```
http://www.ds100.org/sp17/setup
http://cs.brown.edu/courses/cs138/s17/content/docs/git-handout.pdf

#### Department computing system
```ssh username@ssh.cs.brown.edu```
https://cs.brown.edu/about/system/connecting/ssh/

```scp username@ssh.cs.brown.edu:PATH/TO/TEMPLATE .```
https://cs.brown.edu/courses/cs015/docs/WorkingfromHomeSCPSFTP.pdf

### FastX

#### Extracting files
```upzip FILENAME```

```tar -xzvf FILENAME```

### Running the notebook

Go to your working directory (the folder containing the python notebooks)
and run the following.

```
pip3 install virtualenv ENV
source ENV/bin/activate
pip3 install -r requirements.txt
jupyter notebook
```

Click on `lab1.ipynb` for further info.

### Summary

* Read a CSV file `API_ILO_country_YU`
* Show the 12 countries with the highest unemployment rates in 2013
* Show the _country name_ and _country code_ of all rows where:
    * the 2010 unemployment rate is higher than 2014 unemployment rate, and
    * the 2014 unemployment rate is above 20%
* Graph the data and label the axes
* Explore data, answering the 4 _italicized_ questions.

### Submitting assignments

Files to submit

* `lab1.ipynb`


Options:

* git push ...
* data1030_handin

