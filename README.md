# "Revealing contested memory" Master thesis - Github repository
This repository contains the code for the project "Revealing contested memory: Automatic sensitive content detection in colonial photographic archives", aiming at experimenting with the fine-tuning of different Machine Learning models (specifically, Computer Vision models) to assess the feasibility of automatic sensitive content detection in colonial photographic archives.

The project was developed as final thesis for the Master ["Digital Humanities and Digital Knowledge"](https://corsi.unibo.it/2cycle/DigitalHumanitiesKnowledge), at Alma Mater Studiorum - University of Bologna.

## 🧐 Abstract

## 🎈 Usage
The four Jupyter Notebook files showcase the different phases of the project: from the annotated data (which was annotated through Label Studio) to the error analysis of the fine-tuned ML models.

* `1_data_cleaning.ipynb`
  - Data cleaning and processing performed on the annotated data (in the form of CSV files, one for each archival collection) to prepare it for the creation of the dataset: specifically, corrupted images were deleted, unnecessary information was removed to improve readability, new columns with information on the collection of provenance of each image were added, and the files were all moved to a common folder `pictures` with all the information stored in a new `index.csv` file
* `2_dataset_creation.ipynb`
  -  The prepared data was split into three sets (namely: train, validation, and test sets), updating the information in the `index.csv` file. Given the data imbalance, this operation was performed through a stratified split: the class proportions of the dataset population are thus preserved and the risk of not having any instance of the least populated class in the train set is avoided. Finally, images are split in different folders based on their set and class: the dataset, therefore, has a folder-based structure.
* `3_training.ipynb`
  - Experimenting with the ResNet architecture with different hyperparameter configurations. The best performing model is then validated and evaluated on the test set via precision, recall, f1 (both micro and macro average) and accuracy and confusion matrices are produced.  All of the experiments are accessible for further examination on a public interactive Weights & Biases [dashboard](https://wandb.ai/ombrini/binary-classification-rcm?workspace=user-ombrini).
* `4_error_analysis.ipynb`
  - For each class of the test set, the model's predictions (and the predicted score for each class for each instance) are analysed in order to understand the possible errors in detection

## ⛏️ Requirements
- Python 3.11.5

Run the command:
```
pip install -r requirements.txt
```
