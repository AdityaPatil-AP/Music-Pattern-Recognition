# Music Pattern Recognition

Music Pattern Recognition is a project aimed at detecting songs based on their melodies using advanced pitch estimation models and matching techniques.

## Problem Statement

The task of Music Pattern Recognition is to detect a song played, recorded, sung, or played on an instrument from a database of songs. The goal is to develop a system that can accurately identify songs based on their melodies, even if the songs are performed in different musical scales.

## Motivation

Many people often come across catchy tunes but struggle to find the exact match using traditional search methods. Existing systems like Google's "Hum to Search" feature or Shazam have limitations and may not provide accurate results. Music Pattern Recognition aims to address these challenges and improve song recognition technology.

## Features

1. **Pitch Estimation using Crepe and Pyin Models:** The project utilizes advanced models like Crepe and Pyin for estimating the pitch or fundamental frequency of the audio samples.

2. **Mapping Pitch to Notes:** After obtaining the pitch values, they are mapped to musical notes, such as A, B, C#, etc.

3. **Note Sequence Generation:** The mapped note values from each audio sample are combined to form a sequence of notes representing the melodic structure of the song.

4. **Matching with Database using Edit Distance:** The note sequence or melody representation of the input audio is stored in a database or compared against a pre-existing database of known songs. The matching process is performed using the Levenshtein edit distance algorithm.

5. **Scale-Independent Detection:** The Music Pattern Recognition model aims to accurately estimate the pitch of a sound regardless of the musical scale in which it is performed.

<p align="center">
   <img src = "https://github.com/AdityaPatil-AP/Music-Pattern-Recognition/blob/main/Documentation_Paper/System_Workflow.png">
</p>

## Methodology

### Approach 1 (Using Pyin Library):

1. **Preprocessing:** The audio signal is preprocessed to remove silences, background noise, or unwanted segments that are not relevant to the analysis. Endpoint detection is applied to accurately identify the start and end points of meaningful portions of the signal.

2. **Pitch Estimation with Pyin:** The Pyin algorithm is utilized to estimate the pitch or fundamental frequency of each windowed segment of the audio. Median filtering is applied to obtain consistent pitch values throughout the analysis.

3. **Note Sequence Extraction:** Individual notes that span across multiple frames are treated as a cohesive unit. After obtaining the note sequence from the audio analysis, it is used to perform a matching process against the songs stored in the database.

<p align="center">
   <img src = "https://github.com/AdityaPatil-AP/Music-Pattern-Recognition/blob/main/Documentation_Paper/Pitch-Detection.jpg">
</p>

### Approach 2 (Using Crepe Model):

1. **Pitch Estimation with Crepe:** The Crepe model is employed to estimate the pitch or fundamental frequency of each windowed segment of the audio. Peak values or local maxima values for average amplitudes are extracted to identify the highest frequency values.

2. **Mapping to Notes:** The peak frequency values are mapped to musical notes. Each note is associated with the highest frequency value found in a predetermined neighborhood around the peak location.

3. **Note Sequence Generation:** The mapped note values from each windowed segment are combined to form a sequence of notes representing the melodic structure of the song.

4. **Matching with Database:** The note sequence generated from the input audio is matched against the note sequences of the songs stored in the dataset. The Levenshtein edit distance algorithm is applied to calculate the similarity between the sequences.

<p align="center">
   <img src = "https://github.com/AdityaPatil-AP/Music-Pattern-Recognition/blob/main/Documentation_Paper/Crepe-Average-Amplitude.jpg">
</p>

## Tools and Technologies

- Crepe: A pitch estimation model for accurately estimating the pitch or fundamental frequency of audio samples.
- Pyin: A pitch estimation algorithm that provides pitch values for each windowed segment of the audio.
- IPython: An interactive computational environment for running Python code and creating interactive data visualizations.
- Librosa: A Python library for audio analysis and feature extraction, used for preprocessing and analyzing audio signals.
- PyDub: A simple and easy-to-use audio processing library for manipulating audio files, used for audio trimming and processing.

## Conclusion

The Music Pattern Recognition project aims to improve existing systems such as Google's "Hum to Search" feature and Shazam by accurately detecting songs based on their melodies. By utilizing advanced pitch estimation models, mapping pitch to notes, generating note sequences, and matching against a database, the system provides an effective solution for song recognition. The scale-independent detection enables the model to estimate the pitch of a sound regardless of the musical scale in which it is performed.

## Future Scope

The Music Pattern Recognition project has several avenues for future exploration. Some potential areas for enhancement include:

1. Whistling and Humming Recognition:
   - Incorporating recognition capabilities for melodies expressed through vocalizations like whistling or humming.

2. Clustering and Categorization:
   - Utilizing clustering techniques to group similar patterns and motifs, aiding in organizing and categorizing music data.

3. Initial Frequency Variation:
   - Accounting for initial frequency variation in the analysis to accommodate different musical performances.

4. Analysis of Multiple Versions:
   - Analyzing multiple versions of a song to gain insights into variations in interpretation and arrangement.

By pursuing these directions, the Music Pattern Recognition project can enhance its versatility, adaptability, and understanding of music patterns, contributing to a more comprehensive music recognition system.

## Contributors

- Aditya Patil
- Anuja Deshpande
- Dev Bohra
- Surabhi Deshpande
