# "Revealing contested memory" master thesis - github repository
This repository contains the code for the project "Revealing contested memory: Automatic sensitive content detection in colonial photographic archives", aiming at experimenting with the fine-tuning of different Machine Learning models (specifically, Computer Vision models) to assess the feasibility of automatic sensitive content detection in colonial photographic archives.
The project was developed as final thesis for the Master ["Digital Humanities and Digital Knowledge"](https://corsi.unibo.it/2cycle/DigitalHumanitiesKnowledge), at Alma Mater Studiorum - University of Bologna.

## 🧐 Abstract
*Although many European archival institutions hold plenty of visual materials on colonial warfare and domination, these assets are often difficult to access and use. Colonial records are often rendered inaccessible due to not only privacy, copyright, commercial and technical issues, but also to ethical concerns: when handling such unsettling and sensitive content, a discussion on the ethics of care and looking should be addressed. Moreover, the metadata of these materials is often historically charged and shaped by the colonial gaze of the time, providing insufficient or plain wrong contextualisation to the content, and perpetuating the depicted violence even during present-day fruition of these archival records. In this context, the use of Artificial Intelligence (AI) can assist in the detection of sensitive contents, transforming the way scholars and normal users handle large-scale digital collections and helping them confront possibly disturbing content. This thesis project aims at experiment with the fine-tuning of different Machine Learning (ML) models to assess the feasibility of automatic sensitive content detection in colonial photographic archives.
Given the complex and sensitive nature of the source data and the possible ethical pitfalls of
ML, one of the fundamental aspects of this research has been a thorough discussion on the problem definition, taking into account different insights coming from archival sciences, ethics of care and looking, and post-colonialism, and directly inspecting the raw data in parallel with the annotation process. This theoretical framework was then used to interpret the performance of the ML models employed, whose results were processed through a phase of error analysis. The insights gained through this project will be used as a starting point for further research and applications by cultural institutions.*

## 🎈 Usage
The five Jupyter Notebook files showcase the different phases of the project: from the annotated data (which was annotated through Label Studio) to the error analysis of the fine-tuned ML models.
* `1_data_cleaning.ipynb`
  - Data cleaning and processing performed on the annotated data (in the form of CSV files, one for each archival collection) to prepare it for the creation of the dataset: specifically, corrupted images were deleted, unnecessary information was removed to improve readability, new columns with information on the collection of provenance of each image were added, and the files were all moved to a common folder `pictures` with all the information stored in a new `index.csv` file
* `2_dataset_creation.ipynb`
  -  The prepared data was split into three sets (namely: train, validation, and test sets), updating the information in the `index.csv` file. Given the data imbalance, this operation was performed through a stratified split: the class proportions of the dataset population are thus preserved and the risk of not having any instance of the least populated class in the train set is avoided. Finally, images are split in different folders based on their set and class: the dataset, therefore, has a folder-based structure.
* `3_training.ipynb`
  - Experimenting with two different architectures (ViT and ResNet) for the finetuning of the model; after the training, the models are evaluated via precision, recall, f1 (both micro and macro average) and accuracy and confusion matrices are produced 
* `4_error_analysis.ipynb`
  - For each class of the validation set, the images's predictions produced by the model (and the predicted score for each class for each instance) are analysed in order to understand the possible errors in detection

## ⛏️ Built using
Python v. 3.12.0 **(CHECK)**
🤗 Hugging Face libraries `datasets`, `transformers`, `evaluate`

