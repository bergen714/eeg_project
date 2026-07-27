# Detecting left vs right hand imagery from EEG recordings in PhysioNet dataset

## Signal Processing Pipeline for the PhysioNet MMIDB dataset

This project extracts meaningful information from noisy EEG signals to distinguish left vs right hand movement. It walks through the full analysis pipeline using the MNE Python library. The pipeline in this project utilizes bandpass filtering, ICA-based artifact extraction, Welch's method for power spectral density estimation, event-related desynchronization (ERD) analysis, and classification with SVM and Random Forest.

If you want to learn EEG signal processing, explore motor imagery BCIs, or looking for a working example of the MNE-Python library on real recordings, this repository is for you. It includes one Jupyter notebook for data preprocessing and other for band analysis and imagery classification. There is also an interactive dashboard for exploring the features. The graphs are located inside the 'plots' folder.


## Limitations
While doing the independent component analysis, it only picked up on one independent component among 20. This likely resulted in contrasting results in the ERD feature significance analysis, where alpha and beta bands didn't show significant lateralization. Instead, the delta frequency, which is mostly active during sleep, is mostly identified with that behaviour. This might probably be because the ICA failed to remove other artifacts.
