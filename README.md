Prize Winning Ensemble Model for Kaggle See-Click-Fix Contest
============================================================
Prize winning solution to the SeeClickFix contest hosted on Kaggle, developed by teammates Bryan Gregory and Miroslaw Horbal. The purpose of the contest was to train a model (as scored by RMSLE) using supervised learning that will accurately predict the views, votes, and comments that an issue posted to the www.seeclickfix.com website will receive.
My teammate and I used this ensemble code base to combine our top ranked individual models to create a prize-winning solution, defeating >500 other teams and winning a prize of $1,000.


More contest info here: http://www.kaggle.com/c/see-click-predict-fix

In-depth code description here:  http://bryangregory.com/Kaggle/DocumentationforSeeClickFix.pdf

"How I Did It" blog post here: http://bryangregory.com/Kaggle/Kaggle-SeeClickFix-HowIDidIt.pdf

Description
=============
Code for generating an ensemble submission using base submission files generated by our team's individual models, which are located in subfolders under /Bryan/ and /Miroslaw/. The code uses segment based averaging to combine the submissions, based on 5 primary segments identified in the data (remote_api, Chicago, Oakland, New Haven, and Richmond). 

The code also has options to perform averaging in log space (log transformations are performed prior to averaging) and to apply final scalars to the ensemble predictions. Both of these settings were found to increase model accuracy and were used in our winning submission, therefore those settings are defaulted to on.

Independent code repositories for the individual models are available here:

Bryan's model: https://github.com/theusual/kaggle-seeclickfix-model

Miroslaw's model: https://github.com/beegieb/kaggle_see_click_fix

Usage
========
Ensemble weights for each segment of data are stored in SETTINGS.json along with the filepaths for the base input submission files and other misc. settings. Note that with regards to weights base submission 0 corresponds to Bryan's model and base submission 1 is Miroslaw's model.

Prior to running, submission files from the base models must already exist and have the correct file path set in SETTINGS.json.  If the submission files do not exist, then the individual models must first be ran from within their sub folders to create the base submission files.

To run the ensemble code and generate ensemble submission:

      >>> python main.py
      
Requirements
================
      FOR ENSEMBLE CODE ONLY:
      PYTHON >= 2.6
      PANDAS >= .11
      NUMPY

      FOR INDIVIDUAL MODEL CODE:
      PYTHON >= 2.6
      PANDAS >= .11
      NUMPY
      SKLEARN >= .13
      SCIPY >= .12
