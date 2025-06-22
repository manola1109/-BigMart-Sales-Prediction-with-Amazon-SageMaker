# BigMart Sales Prediction with Amazon SageMaker

![AWS SageMaker](https://img.shields.io/badge/Amazon_AWS-FF9900?style=for-the-badge&logo=amazonaws&logoColor=white)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![scikit-learn](https://img.shields.io/badge/scikit--learn-%23F7931E.svg?style=for-the-badge&logo=scikit-learn&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?style=for-the-badge&logo=jupyter&logoColor=white)

**Created By**: manola1109  
**Last Updated**: 2025-06-22 19:16:14

## 📊 Project Overview

This project demonstrates how to build, train, and deploy a machine learning model to predict sales at BigMart stores. The solution uses Amazon SageMaker for model training and deployment, with both Amazon SageMaker built-in algorithms and local model training with scikit-learn.

## 🎯 Problem Statement

The goal is to build a predictive model to forecast BigMart store sales based on various product and store attributes. This project involves:

1. Pre-processing the data, including handling categorical variables and missing values
2. Building a regression model to predict sales
3. Deploying the model using Amazon SageMaker endpoints
4. Using the endpoint for real-time predictions

## 📚 Dataset Description

The dataset contains the following fields:

| Variable | Description |
| --- | --- |
| Item_Weight | Weight of the product |
| Item_Fat_Content | Whether the product is low fat or not |
| Item_Type | Type of Item (Dairy, Drinks, Fruits, Others) |
| Item_MRP | Maximum Retail Price (list price) of the product |
| Outlet_Size | The size of the store in terms of ground area covered |
| Item_Outlet_Sales | Sales of the product in the particular store. This is the outcome variable to be predicted. |

## 🔧 Technical Implementation

This project implements two approaches for model training and deployment:

### Approach 1: SageMaker XGBoost Built-in Algorithm
- Train a model using SageMaker's built-in XGBoost algorithm
- Deploy the trained model to a SageMaker endpoint
- Use the endpoint for real-time predictions

### Approach 2: Local Training and Custom Deployment
- Train a Random Forest Regressor locally using scikit-learn
- Save and package the model with a custom inference script
- Deploy the packaged model to a SageMaker endpoint
- Use the endpoint for serving predictions

## 🚀 Project Structure

- `big_mart_sales_prediction.ipynb` - Main Jupyter notebook with all code and documentation
- `script.py` - Inference script for the custom model deployment
- Data preprocessing pipeline and model training code
- Model evaluation metrics and visualizations
- SageMaker deployment configuration

## 🖥️ Setup and Execution

1. **Environment Setup**
   - Launch an Amazon SageMaker Notebook instance
   - Clone this repository
   - Open the Jupyter notebook

2. **Data Preparation**
   - Load and explore the dataset
   - Handle missing values
   - Encode categorical variables
   - Split data into training and validation sets

3. **Model Training**
   - Train a local Random Forest model
   - Package the model for SageMaker deployment

4. **Model Deployment**
   - Deploy the model as a SageMaker endpoint
   - Configure the endpoint for real-time inference

5. **Model Inference**
   - Send prediction requests to the endpoint
   - Evaluate prediction results

## 📈 Model Performance

The Random Forest Regression model achieves:
- R² score: ~0.56
- Root Mean Squared Error (RMSE): ~1042
- Mean Absolute Error (MAE): ~821

## ✅ Key Features

- Comprehensive data preprocessing pipeline
- Model training with hyperparameter tuning
- Real-time prediction capabilities
- Detailed visualization of results
- Robust error handling and fallback options

## 🔗 AWS Services Used

- Amazon SageMaker for model training and deployment
- Amazon S3 for storing model artifacts and data
- AWS IAM for access management
- Amazon ECR for container registry

## 🛠️ Technologies

- Python 3.8+
- scikit-learn
- pandas
- numpy
- matplotlib & seaborn for visualization
- Amazon SageMaker SDK

## 📝 Notes

- The notebook supports both ml.t2.medium and other instance types
- Make sure to delete endpoints when not in use to avoid unnecessary charges
- The model artifacts are stored in S3 and can be reused for future deployments
- If the SageMaker endpoint deployment fails, the notebook gracefully falls back to using a local model for predictions

## 📜 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Special thanks to the AWS SageMaker team for the platform
- The original BigMart Sales dataset creators and contributors
