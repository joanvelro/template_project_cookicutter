# Template Project 
## Based on Cookicutter




```
├── LICENSE
├── Makefile                           <- Makefile with commands like `make data` or `make train`
├── README.md                         <- The top-level README for developers using this project.
├── data 
│    └── external                     <- Data from third party sources. 
│    └── interim                      <- Intermediate data that has been transformed. 
│    └── processed                    <- The final, canonical data sets for modeling. 
│    └── raw                          <- The original, immutable data dump. 
│    
│ 
├── docs                              <- A default Sphinx project; see sphinx-doc.org for details 
│ 
├── models                            <- Trained and serialized models, model predictions, or model summaries. Guardar lo que sale de los experimentos. Reaprovechar en lo que se pueda el código de src.  
│ 
├── notebooks                         <- Jupyter notebooks. Naming convention is a number (for ordering), 
│                                       the creator's initials, and a short `-` delimited description, e.g. 
│                                       `1.0-jqp-initial-data-exploration`. 
│
├── unittest                          <- Unitary test
│     └── basic_test.py               <- Basic unitary test
│     └── advanced_test.py            <- advanced unitary test
│
├── references                        <- Data dictionaries, manuals, and all other explanatory materials. 
│     └── config.ini                  <- advanced unitary test
│
├── reports                           <- Generated analysis as HTML, PDF, LaTeX, etc. 
│      └── figures                    <- Generated graphics and figures to be used in reporting
│      └── logs                       <- logs
│ 
├── requirements.txt                  <- The requirements file for reproducing the analysis environment, e.g. 
│                                         generated with `pip freeze > requirements.txt` 
│
├── setup.py                          <- Make this project pip installable with `pip install -e` 
│
├── src                               <- Source code for use in this project. 
│    ├── __init__.py                  <- Makes src a Python module 
│    │   
│    ├── data                         <- Scripts to download or generate data sets
│    │     └── make_dataset.py
│    │
│    ├── features                     <- Scripts to turn raw data into features for modeling
│    │     └── build_features.py
│    │
│    ├── models                       <- Scripts to train models and then use trained models to make
│    │     └── predict_model.py
│    │     └── train_model.py
│    │
│    └── visualization                <- Scripts to create exploratory and results oriented visualizations
│          └── visualize.py
│
├── Dockerfile                        <- Dockerfile 
└── tox.ini                           <- tox file with settings for running tox; see tox.testrun.org 


 ```

* To build up the python environment using Docker:
```
RUN pip install requirements.txt
```

* Documentation requires:
```
pip install Sphinx
pip install rinohtype
```
* If not created docs folder, create it:
```
mkdir docs
cd docs
```
* Set up sphinx
```
sphinx-quickstart
```
* - Open source/conf.py
* Configure path to root directory
```
sys.path.insert(0, os.path.abspath('..//..'))
```
  
* Add Rinohtype to the list of extension
```
'rinoh.frontend.sphinx'
```

* Open the index.rst and change the content to the following

```
Documentation for the Code
**************************
.. toctree::
   :maxdepth: 2
   :caption: Contents:

Main
===================
.. automodule:: main
   :members:

Functionality 1
=====================
.. automodule:: src.one
   :members:

Functionality 2
=================
.. automodule:: src.two
   :members:

Functionality 3
===================
.. automodule:: src.three
   :members:
```

* where automodule correspond with the name of the python file 
```
"""
.. module:: Exploratory Data Analysis
   :synopsis: Exploratory Data Analysis of the data set that contains the crimes in the city
    Data path and other configuration settings are indicated in config.ini

.. moduleauthor:: Jose Angel Velasco - (C) Tessella Spain by Capgemini Engineering - 2021
"""
```

* Each function is documented with his structure
```
"""
    def function(input_arg1, input_arg2, input_arg3)
    
        **Funtion title**

        Function description
        
        :param input_arg1: description
        :param input_arg2: description
        :param input_arg3: description
        :return: description
    """
```
* Handle errors with try-except in every function
```
try:
    ...
    return error=0, output_arg
except Exception as exception_msg:
    error = 1
    return error, output_arg 
    print.error('(!) Error in function_name:{}'.format(str(exception_msg)))   
```


* Still inside the docs directory run, Create the HTML documentation files.
```
make html
```
```
make latex
```
* Pdf documentation
```
sphinx-build -b rinoh source _build/rino
```

_(C) Tessella Spain by Capgemini Engineering - 2021_
