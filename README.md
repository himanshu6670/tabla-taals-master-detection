Automatic Detection and Classification of tabla talas from the Indian Classical music

Introduction
This project work aims at developing a system that would be able to first detect a tabla tala from a mix(a song) of an Indian or Carnatic Classical Music and then classify the tala. Tala is a specific pattern which occurs in all of the Indian Classical Music and Tabla is the percussive accompanying instrument.

Motivation
The work done by people around the world from the Music Information Retrieval (MIR) community revolves around the western music, their genres, and their instruments, but no significant work has been carried around Indian Classical Music and specifically tabla. The main objective of the project was to make the system real-time. The attempt to making the system real-time has not been done so far. Also, this could be the starting point to study the several prospects of Indian Classical Music. To the best of our knowledge, there have been only a few attempts on tala classification using Deep Learning and making it real-time. Also, the attempts made in bol transcription use the classical machine learning techniques which may not be able to make classification robust.

Methods used
     Models
     Convolutional Neural Network
     Long Short-Term Memory Network
     Signal Processing
     Downsampling (from 44100 to 16000)
     Noise Threshold Detection (Using envelope detection)
     Harmonic-Percussive Source Separation HPSS
     
File description
PNstreamsetup.py - Audio backend for live audio and FFT.
GUI.py - QtDesigner generated code converted to Python using pyuic
Vocalseparation.py - Implementation of vocal separation as shown here.
dataops.py - Perform pre-processing on data.
model.py - Models and pickles form here.
predict.py - Predict on a sample using this.
main.py - Real-time visualisations, recording and classification

Getting Started
Clone this repository git clone https://github.com/pranav6670/Detection-Classification-of-Tabla-taals.git.

Data is stored in wavfiles diectory. Check-out the data. There are 10 classes of talas. A test.csv is included in the directory

First run the dataops.py script which will pre-process the data which includes, first, downsampling the data and then cleaning it(noise threshold detection).

Then create two folders named models and pickles into the directory.

Run model.py to form pickles out of the data and start training. The cfg.py can be used to adjust the parameters of MFCC function. In model.py, config.mode == 'conv' will select the CNN model while config.mode == 'rec' will select the LSTM model. The difference between these is only the shape of input data to the model. Once pickles are formed for both the models, the data dosen't load again the next time, saving alot of time. The models are easy to modify.

Under models directory, you will find the conv.model and rec.model formed, after training. Use these models to predict using predict.py

Also run main.py after training to do the classification real-time.

