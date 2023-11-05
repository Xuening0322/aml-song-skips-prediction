# Spotify Song Skip Prediction

This repository contains the code for our project "Thank You, Next: Predicting Song Skips for Personalized Music Recommendations", where we apply machine learning algorithms to predict song skips on Spotify. The aim is to enhance the user experience on music streaming platforms by providing more accurate recommendations.

## Project Structure

The repository is structured with two main Jupyter Notebooks:

- `Spotify_Song_Skipping_Prediction_Part_I_EDA.ipynb`: Contains the exploratory data analysis of the Spotify Sequential Skip Prediction Dataset.
- `Spotify_Song_Skipping_Prediction_Part_II_LightGBM.ipynb`: Includes the modeling process using Gradient Boosted Trees, LSTM, Bi-LSTM, and Transformer models.

## Dataset

For this project, we utilize the [Spotify Sequential Skip Prediction Dataset](https://www.aicrowd.com/challenges/spotify-sequential-skip-prediction-challenge/dataset_files), introduced by Brost et al. in 2019. This extensive dataset contains approximately 130 million listening events, with each session encompassing up to 20 songs. User behavior features and track IDs are provided for the first half of the sessions, while only track IDs are available for the second half. Track IDs link to a track's acoustic features, which can be obtained via the Spotify API. User behavior features include actions such as whether the user paused and the hour of the day, while acoustic features cover aspects like danceability and tempo.

### Downloading the Data

#### Part I - Initial Data:

To begin working with the data, you will need to download the following files:

- `Training_Set.tar.gz` (56 GB): Contains the user listening sessions.
- `Track_Features.tar.gz` (1.2 GB): Contains metadata and acoustic features for the tracks.

The code to download the `Training_Set.tar.gz` is included in the `Spotify_Song_Skipping_Prediction_Part_I_EDA.ipynb` notebook. However, you will need to manually download the `Track_Features.tar.gz` from the [dataset's webpage](https://www.aicrowd.com/challenges/spotify-sequential-skip-prediction-challenge/dataset_files).

#### Part II - Processed Data:

The `spotify_skip.csv` file, which is roughly 2.02 GB, contains processed data from Part I. If you wish to directly use this preprocessed data for Part II - the modeling phase - you can download mine from the following Google Drive link: [Spotify Skip Data CSV](https://drive.google.com/file/d/1_7DlNTZOpBA1lPlf5j4U3ssoZTRr-C2d/view?usp=sharing)

### Using the Data

The notebooks are designed to work with this dataset in a specific sequence:

1. The `Spotify_Song_Skipping_Prediction_Part_I_EDA.ipynb` notebook assumes you have downloaded and extracted the `Track_Features.tar.gz` file, which will be used for exploratory data analysis.

2. The `Spotify_Song_Skipping_Prediction_Part_II_LightGBM.ipynb` notebook uses the results from the EDA phase, encapsulated in the `spotify_skip.csv` file. You can either generate this file by completing the EDA notebook or download it directly if you wish to start with the modeling.

Please note that due to the large size of these files, it is recommended to have a stable internet connection and sufficient storage space before attempting to download the dataset.

## Exploratory Data Analysis (EDA)

In the `Spotify_Song_Skipping_Prediction_Part_I_EDA.ipynb` notebook, we perform a comprehensive analysis of the dataset provided by Spotify. We visualize and understand the patterns and correlations in the data, which includes:

- User behavior features like pauses, hour of the day
- Track features such as danceability, tempo, etc.
- Session homogeneity and skip trends

Visualizations such as pair plots and characteristic distributions are used to elucidate the data's structure.

## Modeling

The `Spotify_Song_Skipping_Prediction_Part_II_LightGBM.ipynb` notebook walks through our approach to predicting song skips. It starts with establishing a baseline with LightGBM and progresses through more sophisticated techniques:

- Gradient Boosted Trees for initial predictions
- LSTM and Bi-LSTM for sequential data modeling (currently working on)
- Transformers for capturing long-range dependencies in the data (currently working on)

Each model's performance is evaluated using accuracy, precision, recall, F1 score, and ROC-AUC score metrics.