Binary Event Classification on UUSS Data
===============================================
</p>

<p align="left">
<b><a href="#overview">Overview</a></b>
|
<b><a href="#set-up">Set-Up</a></b>
|
<b><a href="#use">Use</a></b>
|
<b><a href="#credits">Credits</a></b>

</p>


Overview
-----

Use a model (CNN,LSTM or combined) trained on events within Utah (2012-2017) to make predictions on new events. 
The model takes event spectrograms (1-3 channel; 90s) and classifies them as either quarry blasts or local earthquakes based on their spectral content.

<p align="center"><img src="https://github.com/quapity/UUSS_LSTM_classification/raw/master/figures/screen1.png"></p>

Set-Up
------------

### Dependencies
* Relies on Numpy,Scipy,Pandas. Most can be installed with pip or ship with Anaconda
* Waveform data from [Obspy]  
* Database files from UUSS 
    - eventlist, filename: dbcat 
    - picktables by event type, filenames: le,qb
* I use the super handy [adjustText]to plot non-overlapping text on map
    - pip install adjustText
* And I gave you some clumsy plotting functions that use Basemap
    - [Basemap Toolkit]
* Load the models (HDF5, built with Tensorflow) using Keras
    - [Tensorflow]
    - [Keras]
    
  
Use
------------

### General Use

* Once you have db files (dbcat,le,qb) you can call any function in the pipeline. The following will get you a map and table for the first 20 events in your database file:
   - data = preproc_data(parse_dbselect(),num_events=20)
   - plt_events(data)
   - make_stats(data)
   
The stats table saves to the local dir and looks like this:

![ScreenShot](https://github.com/quapity/UUSS_LSTM_classification/raw/master/figures/screen2.png)

* Still need more help/details/info?? 
   - [Jupyter] notebook [here](https://github.com/quapity/UUSS_LSTM_classification/blob/master/tutorial.ipynb)

Credits
------------
Reference: Linville et al., 2019, in press (GRL accepted manuscript)

* [Tensorflow]
* [Keras]
* [Obspy]

[adjustText]:https://github.com/Phlya/adjustText
[Basemap Toolkit]:https://matplotlib.org/basemap/
[Jupyter]:http://jupyter.org/
[Keras]:https://keras.io/
[Tensorflow]:https://www.tensorflow.org/
[Obspy]:https://github.com/obspy/obspy/wiki


