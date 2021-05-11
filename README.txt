Music Classifier - Singer Identifier

2020 Version
Release Date: December 07, 2020

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

README CONTENTS

1.1 Introduction
1.2 Description
1.3 Challenges Faced
1.4 Future Work

2.0 Jupyter Notebooks
2.1 CSV Files

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1.1 Introduction


Introduction to JioSaavn and Deezer:

Founded in 2007, Jio Saavn is an online music streaming service catering its services to users across the globe by having its headquarters
in Mumbai (India) and New York (USA). Jio Saavn is available to the users on Android, Apple, and Microsoft Windows platforms apart from
the option to use it as a web-application. It provides its users with songs in English and Indian regional languages. One does not need to
have an account with ‘Jio Saavn’ in order to browse the songs from its mobile or web application. 
Reliance Industries Limited is the parent organization for Jio Saavn.

Being founded in 2007, Deezer is also an online music streaming service. With its headquarters in Paris (France),
services are being provided to the users in more than 180 different countries. Similar to Jio Saavn, Deezer is also available on Android,
Apple, and Microsoft Windows platforms and can also be accessed as a web-application. We need to create an account to access the songs and
playlists on the Deezer website or mobile application.

License Information:

Licensed under © 2019 Saavn, LLC.
Licensed under © 2020 Deezer.

For details, see: 

https://www.jiosaavn.com/corporate/privacy/
https://www.deezer.com/legal/cgu

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1.2 Description

Audio Data has been extracted from JioSaavn and Deezer websites separately for Artists and Genres.

Artists included are - 
1) Adam Levine
2) Drake
3) Justin Bieber
4) Selena Gomez
5) The Weeknd
6) Arijit
7) Atif Aslam
8) Sonu Nigam
9) Anurag
10) Armaan
11) Geetha
12) Sid SriRam


Genres included are -
1) HipHop (English)
2) Rock (English, Telugu, Hindi)
3) Romantic (English, Telugu, Hindi)
4) Workout (English, Telugu, Hindi)

Languages included are -
1) English
2) Telugu
3) Hindi

Below are the attributes extracted for each song -
‘Song Name’, ‘Singer Name’, ‘Song Genre’, ‘Album Name’, ‘Album URL’, ‘Song URL’, ‘Release Year’, ‘Song Duration’, ‘Download Link’, ‘Song ID’.

MP3/MP4 version Audio files are then converted into WAV format for the ease of processing.

This WAV file is fed to Spleeter Module which separates vocals and acoustics from the audio file. Thus giving out two different WAV files as output.

Using Librosa package, spectral features for these audio files have been extracted which will then be passed on to the machine learning model at a later stage.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1.3 Challenges Faced and Overcomed

In the initial stages of our project, we had several options to consider for data harvesting like AudioDB, JioSaavn, Deezer, Spotify, SoundCloud etc.
Based on the terms and conditions of each website, it has been decided to proceed with JioSaavn and Deezer.

Dataset was huge, so understanding the importance of all variables was difficult.

Outlier analysis tuned differently and produced various results, tuning to an optimal value was a challenge.

Splitting and Extracting features from WAV file was time-consuming.

Issue while using Librosa.Load function - Sndfile.dll has no attribute error has been encountered. Had to change few lines of code in Librosa package to resolve.

Owing to huge space occupied by each instance of the song (5 second window), we couldn’t afford to save .wav file of each instance separately. 
Instead, used a single buffer storage for all instances and  extracted the required features.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

1.4 Future Work

1) To build separate models for Singer Identification and Genre Identification
2) Training of CNN Model
3) Testing of CNN Model
4) Hyper-Parameter Tuning
5) Metrics Evaluation
6) Building Speech to Text conversion
7) To incorporate above model into an end-to-end application. (If time permits)

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

2.0 Jupyter Notebooks


DataCollectionJioSavan_English.ipynb 			- Code in this notebook includes the logic to collect and download audio data files and song details for English language.
DataCollectionsRegional Languages.ipynb 		- Code in this notebook includes the logic to collect and download audio data files and song details for Indian regional languages.
Deezer data collection and audio file download		- Code to extract/download audio data files along with necessary song details from Deezer is included in this notebook.
Converting audio files from mp3, mp4 to wav.ipynb 	- This R script is used in order to convert the MP3/MP4 audio files into WAV format as the packge in python (ffmpeg) for this purpose has been depricated.
Separating vocals data from artist audio files.ipynb 	- This notebook covers the code for separating vocals and instrumental music from the input audio file using the Spleeter module.
Features Extraction        				- This notebook comprises of code to extract all the features from the audio data.
Data Merging.ipynb					- Logic behind generating 'final_data.csv' file by merging artist and genre data is included in this notebook.
							  (This file is later split to artist and genre data separately for EDA and further processing of the model.)
EDA_Part1_Artist_V1.ipynb 				- This notebook includes all our code for artist data (Visualization, PCA..) along with the description of what the code in each cell does.
EDA_Part2_Genre_V1.ipynb  				- This notebook includes all our code for genre  data (Visualization, PCA..) along with the description of what the code in each cell does.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

2.1 CSV Files


Final_data.csv provides the data of all te extracted features for artists and genres combined.

This data is then split into Artist_Data.csv and Genre_Data.csv separately for exploratory data analysis.

--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

<end of file>



