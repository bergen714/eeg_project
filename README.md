# Detecting left vs right hand imagery from EEG recordings in the PhysioNet dataset

## Signal Processing Pipeline for the PhysioNet MMIDB dataset

This project extracts meaningful information from noisy EEG signals to distinguish left vs right hand movement. It walks through the full analysis pipeline using the MNE Python library. The pipeline in this project utilizes bandpass filtering, ICA-based artifact extraction, Welch's method for power spectral density estimation, event-related desynchronization (ERD) analysis, and classification with SVM and Random Forest.

If you want to learn EEG signal processing, explore motor imagery BCIs, or are looking for a working example of the MNE-Python library on real recordings, this repository is for you. It includes one Jupyter notebook for data preprocessing and another for band analysis and imagery classification. There is also an interactive dashboard for exploring the features. The graphs are located inside the 'plots' folder.


## Limitations
During independent component analysis, 20 components were identified, but only 1 was flagged as an eye-blink artifact. Additional muscle artifacts were also identified in other channels, but most muscle artifact scores were below 80%, which likely didn't impact noise removal compared to the eye artifacts. This likely explains the implausible results in the ERD analysis, where alpha and beta bands didn't show significant contralateral lateralization between channels C3 and C4. Instead, the delta frequency, which is mostly active during sleep, was mostly identified with that behavior.

In a future version, I will attempt to keep the artifacts whose scores are below 50%. The eye-blink artifact's score was above 90%, which was probably because it was able to pick up those artifacts easily from the front two channels. When I used all the channels as a reference to find muscle artifacts, it was probably more difficult to extract high-scoring muscle artifacts than eye-blink artifacts.
