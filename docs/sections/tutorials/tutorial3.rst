Preprocessing
==========

In this tutorial you will learn how to preprocess your RR time series. The resulting preprocessed time series is traditionally called the 'NN' time series.

**Introduction**
----------------------

When loading an RR time series in the HRV module, one of the parameters you need to set is the preprocessing method.

We implemented in **PhysioZoo** three methods (and one combination of methods) for pre-filtering the RR-interval:

  * Range, 
  * Moving average,
  * Quotient,
  * Combined (the combination of the Range and the Moving average filters).

**Why is preprocessing important?**
----------------------
A preprocessing step is usually performed in HRV analysis to filter out suspected ectopic beats, missed beats and artifacts.

The example below shows an ECG segment with some transient noise. Note the miss-detected R-peaks. Leaving these miss-detected R-peaks could lead to the evaluation of incorrect HRV measures.

.. image:: ../../_static/Figure_S2.png


Below, the corresponding RR interval time series that is filtered. The filtering allows to remove the sudden increase and decrease in the RR time series that are caused by the miss-detected beats.

.. image:: ../../_static/Figure_S3.png


**Preprocessing methods in PhysioZoo**
----------------------
  
You can select the preprocessing filter with the dropdown "Preprocessing" located under the Main tab. You can vary the level of preprocessing by using the dropdown "Preprocessing level" located under the Main tab. Three levels of preprocessing are available: Weak, Moderate and Strong. If you want to customize the preprocessing filters further then you can access each of the parameters of each filter by going to Options -> Filtering.

The image below shows an example of a rabbit RR time (blue time series) series which has been filtered over the selected window (green time series) using the Moving average filter .

.. image:: ../../_static/prefiltering_step.png

**Practical remarks**
----------------------

Preprocessing methods are useful to remove local miss-labelled beats caused by noise or sudden drop/increase in RR due to ectopic beats. However, in the presence of large segments of noise it will not help. Rather such large segments of bad quality data should be discarded from the analysis. You can annotate `the quality <../tutorials/tutorial_formats.html>`_ of the electrophysiological time series in order to have this contexttual information when performing HRV analysis.




