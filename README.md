# Hindustani Classical Raga Prediction Model

## Project Overview
This repository contains the implementation of a **Raga Prediction Model** designed specifically for Hindustani Classical Music. The model takes MIDI files as input and predicts the raga based on pitch, duration, and velocity features extracted from the MIDI data. The training dataset was carefully curated from flute concerts of **Pt. Hariprasad Chaurasia**, processed to isolate the flute from accompanying instruments, and converted into MIDI format.

## Workflow
1. **Dataset Preparation**:
   - Extracted audio from YouTube recordings of Pt. Hariprasad Chaurasia.
   - Isolated flute tracks using **Audacity**.
   - Converted the audio to MIDI files using **Melodyne**.
   - Split the MIDI files into 1-minute segments to create the training dataset.

2. **Feature Extraction**:
   - Extracted features include pitch, note duration, and velocity.
   - Computed **Pitch Class Distributions (PCD)** based on Hindustani swara notation (S, r, R, g, G, m, M, P, d, D, n, N).

3. **Model Training**:
   - Trained a **Hidden Markov Model (HMM)** for each raga using its MIDI data.
   - Used `hmmlearn` to fit models for pitch, duration, and velocity.

4. **Testing and Evaluation**:
   - Evaluated the model on test data with unseen MIDI files.
   - Achieved raga predictions based on similarity scores from HMM models.

## Libraries Used
- **[PrettyMIDI](https://github.com/craffel/pretty-midi)**: MIDI file processing and manipulation.
- **Numpy** and **Pandas**: For data handling and analysis.
- **Matplotlib**: For visualizing pitch class distributions.
- **HMMLearn**: For Hidden Markov Model implementation.
- **Scikit-learn**: For additional machine learning utilities.

## Features
1. **Pitch Class Distribution Visualization**:
   - Displays normalized frequencies of Hindustani notes for MIDI files.
   - Provides insight into the structure of the raga.

2. **Hidden Markov Model Training**:
   - Separate models trained for each raga in the dataset.
   - Predictions made by scoring MIDI sequences against trained models.

3. **Accuracy Calculation**:
   - Compares model predictions with actual labels to compute accuracy.


## Prerequisites
Install the required libraries using:
```bash
pip install pretty-midi numpy pandas matplotlib hmmlearn scikit-learn
```
## Results
- The model provides accurate raga predictions based on input MIDI files.
- Accuracy: 100%

## Future Improvements
- Extend the dataset by including more ragas on more instruments and by more artists.
- Explore deep learning models like LSTMs for sequential data.

## Acknowledgements
- Pt. Hariprasad Chaurasia for the inspiring flute performances.
- Audacity and Melodyne for enabling precise audio and MIDI file creation.
