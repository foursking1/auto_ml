.. auto_ml documentation master file, created by
   sphinx-quickstart on Sun Aug  7 20:25:48 2016.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to auto_ml's documentation!
===================================

Contents:

.. toctree::
   :maxdepth: 3

   self
   getting_started.rst
   formatting_data.rst
   analytics.rst
   ensembling.rst
   api_docs_for_geeks.rst

Installation
------------

``pip install auto_ml``


Core Functionality Example
--------------------------

.. code-block:: python

  from auto_ml import Predictor

  col_desc_dictionary = {col_to_predict: 'output'}

  ml_predictor = Predictor(type_of_estimator='classifier', column_descriptions=col_desc_dictionary)
  # Can pass in type_of_estimator='regressor' as well

  ml_predictor.train(list_of_dictionaries)
  # Wait for the machine to learn all the complex and beautiful patterns in your data...

  ml_predictor.predict(new_data)
  # Where new_data is also a list of dictionaries

  ml_predictor.save()
  # Saves the trained predictor to a pickle file in the current working directory.
  # You can load it using pickle.load in any environment with compatible Python versions. This is what you'll want to use for easily transferring from research into production!

Advice
------

Before you go any further, try running the code. Load up some dictionaries in Python, where each dictionary is a row of data. Make a ``column_descriptions`` dictionary that tells us which attribute name in each row represents the value we're trying to predict. Pass all that into ``auto_ml``, and see what happens!

Everything else in these docs assumes you have done at least the above. Start there and everything else will build on top. But this part gets you the output you're probably interested in, without unnecessary complexity.



What this project does
=======================
Automates the whole machine learning process, making it super easy to use for both analytics, and getting real-time predictions in production.

A quick overview of buzzwords, this project automates:

#. Analytics (pass in data, and auto_ml will tell you the relationship of each variable to what it is you're trying to predict).
#. Feature Engineering (particularly around dates, and soon, NLP).
#. Robust Scaling (turning all values into their scaled versions between the range of 0 and 1, in a way that is robust to outliers, and works with sparse matrices).
#. Feature Selection (picking only the features that actually prove useful).
#. Data formatting (turning a list of dictionaries into a sparse matrix, one-hot encoding categorical variables, taking the natural log of y for regression problems).
#. Model Selection (which model works best for your problem).
#. Hyperparameter Optimization (what hyperparameters work best for that model).
#. Ensembling Subpredictors (automatically training up models to predict smaller problems within the meta problem).
#. Ensembling Weak Estimators (automatically training up weak models on the larger problem itself, to inform the meta-estimator's decision).
#. Big Data (feed it lots of data).
#. Unicorns (you could conceivably train it to predict what is a unicorn and what is not).
#. Ice Cream (mmm, tasty...).
#. Hugs (this makes it much easier to do your job, hopefully leaving you more time to hug those those you care about).
