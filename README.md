# federated-learning
Project Overview
This project involves building a machine learning pipeline that predicts property price ranges using various features related to real estate data. The main dataset consists of attributes such as residential space prices, building space prices, and other economic factors like exchange rates. The project follows a federated learning approach for model training, where each client's data is trained independently and then aggregated.

Steps of the Project
Data Preprocessing:

The dataset includes features like unit price of residence space, residence space, unit price of building space, building space, and exchange rate.
A new feature total cost is calculated using the residence and building space prices, along with the exchange rate.
The unit price of residence space and unit price of building space columns are dropped after deriving total cost.
The total cost is then used to assign each property to a price range, creating a categorical target variable called price range.
Label Encoding:

Columns like district and city contain categorical data that need to be converted into numerical form for model training.
The LabelEncoder from Scikit-learn is applied to both the train and test datasets to ensure consistency in encoding.
Model Training (Federated Learning):

A RandomForestClassifier is employed as the model for each client in the federated learning setup.
Each client's data is used to independently train their own model.
After training, model predictions from each client are aggregated using majority voting to generate final predictions.
Model Aggregation:

In this federated learning framework, instead of combining model weights, predictions from all client models are aggregated using a majority voting mechanism. This ensures that each client's local data contributes to the overall prediction in a federated manner.
Evaluation:

The aggregated model is evaluated on validation data, and accuracy scores are calculated to assess model performance.