pyEMU
=====

model-independent FOSM (first-order, second-moment) (a.k.a linear-based, a.k.a. Bayes linear) computer model uncertainty analyses.

[![Build Status](https://travis-ci.org/jtwhite79/pyemu.svg?branch=master)](https://travis-ci.org/jtwhite79/pyemu)

What is pyEMU?
================

pyEMU is a set of python modules for model-independent, user-friendly, computer model uncertainty analysis.  pyEMU is tightly coupled to the open-source suite PEST (Doherty 2010a and 2010b, and Doherty and other, 2010) and PEST++ (Welter and others, 2015, Welter and other, 2012), which are tools for model-independent parameter estimation.  However, pyEMU can be used with generic array objects, such as numpy ndarrays.

Several equations are implemented, including Schur's complement for conditional uncertainty propagation (a.k.a. Bayes Linear estimation) (the foundation of the PREDUNC suite from PEST) and error variance analysis (the foundation of the PREDVAR suite of PEST).  pyEMU has easy-to-use routines for parmaeter and data worth analyses, which estimate how increased parameter knowledge and/or additional data effect forecast uncertainty in linear, Bayesian framework.  Support is also provided for Monte Carlo analyses via an Ensemble and MonteCarlo class, including the null-space monte carlo approach of Tonkin and Doherty (2009).

pyEMU also includes lots of functionality for dealing with PEST(++) datasets, such as:
* manipulation of PEST control files, including the use of pandas for sophisticated editing of the parameter data and observation data sections
* creation of PEST control files from instruction and template files
* going between site sample files and pandas dataframes - really cool for observation processing
* easy-to-use observation (re)weigthing via residuals or user-defined functions
* handling Jacobian and covariance matrices, including functionality to go between binary and ASCII matrices, reading and writing PEST uncertaity files.  Covariance matrices can be instaniated from relevant control file sections, such as parameter bounds or observation weights.  The base Matrix class overloads most common linear algebra operators so that operations are automatically aligned by row and column name.  Builtin SVD is also included in all Matrix instances.
* geostatistical structure support, including reading and writing PEST structure files and creating covariance matrices implied by nested geostatistical structures

Examples
========

Several example ipython notebooks are provided to demostrate typical workflows for FOSM parameter and forecast uncertainty analysis as well as techniques to investigate parameter contributions to forecast uncertainty and observation data worth. Example models include the Henry saltwater intrusion problem (Henry 1964) and the model of Freyberg (1988)

Links
=====

[https://github.com/dwelter/pestpp](https://github.com/dwelter/pestpp)

[PEST - http://www.pesthomepage.org/](http://www.pesthomepage.org/)



References
==========

Doherty, J., 2010a, PEST, Model-independent parameter estimation—User manual (5th ed., with slight additions):
Brisbane, Australia, Watermark Numerical Computing.

Doherty, J., 2010b, Addendum to the PEST manual: Brisbane, Australia, Watermark Numerical Computing.

Doherty, J.E., Hunt, R.J., and Tonkin, M.J., 2010, Approaches to highly parameterized inversion: A guide to using PEST for model-parameter and predictive-uncertainty analysis: U.S. Geological Survey Scientific Investigations Report 2010–5211, 71 p., available at http://pubs.usgs.gov/sir/2010/5211.

Freyberg, D. L. (1988). An exercise in ground-water model calibration and prediction. Ground Water, 26 , 350{360.

Henry, H.R., 1964, Effects of dispersion on salt encroachment in coastal aquifers: U.S. Geological Survey Water-Supply Paper 1613-C, p. C71-C84.

Langevin, C.D., Thorne, D.T., Jr., Dausman, A.M., Sukop, M.C., and Guo, Weixing, 2008, SEAWAT Version 4: A Computer Program for Simulation of Multi-Species Solute and Heat Transport: U.S. Geological Survey Techniques and Methods Book 6, Chapter A22, 39 p.

Tonkin, M., & Doherty, J. (2009). Calibration-constrained monte carlo analysis of highly parameterized models using subspace techniques. Water Resources Research, 45 .

Welter, D.E., Doherty, J.E., Hunt, R.J., Muffels, C.T., Tonkin, M.J., and Schreüder, W.A., 2012, Approaches in highly parameterized inversion—PEST++, a Parameter ESTimation code optimized for large environmental models: U.S. Geological Survey Techniques and Methods, book 7, section C5, 47 p., available at http://pubs.usgs.gov/tm/tm7c5.

Welter, D.E., White, J.T., Hunt, R.J., and Doherty, J.E., 2015, Approaches in highly parameterized inversion— PEST++ Version 3, a Parameter ESTimation and uncertainty analysis software suite optimized for large environmental models: U.S. Geological Survey Techniques and Methods, book 7, chap. C12, 54 p., http://dx.doi.org/10.3133/tm7C12.


How to get started with pyEMU
=============================

I recommend the Anaconda scientific python distribution (FREE!), which includes the dependencies for pyemu, as well as the jupyter notebook:

[https://store.continuum.io/cshop/anaconda/](https://store.continuum.io/cshop/anaconda/])

Once installed, clone (or download) the pyemu repository and run the setup.py script from the command prompt:

`>>>python setup.py install`

Then start the ipython notebook from the command prompt:

`>>>jupyter notebook`

You should then be able to view the example notebooks.

