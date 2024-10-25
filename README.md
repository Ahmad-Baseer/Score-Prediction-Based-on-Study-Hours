---
title: Score Prediction Based On Study Hours
emoji: 📚
colorFrom: purple
colorTo: gray
sdk: streamlit
sdk_version: 1.39.0
app_file: app.py
pinned: false
---

# How to run the application

1. Assuming you have Python installed in your system, after that first you have to run this command: ```pip install -r requirements.txt``` in cmd to install the required libraries.
2. Then you have to run the Prediction_Model file, It will export the prediction model as: ```model.sav```  in your working directory.
3. After having ```model.sav``` you can run ```Web_App.py```, it will create app.py in your working directory.
4. That's all you should have now you have to open cmd in your working directory and run this command: ```streamlit run app.py```, it will run your application locally.
5. Now you can follow any YouTube video to deploy this application.
6. You can use my application here: [Student-Score-Prediction](https://huggingface.co/spaces/AhmadHashim/Student-Score-Prediction) 

# Complete working of this application
## Data Preprocessing
To begin, I printed the head and tail of the dataset to understand its structure and formatting. Next, I obtained a five-number summary using the ```describe``` function, which allowed for a careful examination of the data. Based on these initial insights, the following decisions were made:
1. No additional feature engineering or preprocessing was needed for this dataset. The data is already well-structured, properly distributed, and contains only the two required columns. This picture illustrates all of these insights.
![image](https://github.com/user-attachments/assets/8273eb1d-48e0-4359-8fde-7cc16efdac35)

## Prediction Algorithm
So, directly jumping into the prediction algorithm. First, the input (```X```) and output (```y```) variables were defined, representing ```Hours``` and ```Scores```, respectively. The data was then split into training and test sets using the ```train_test_split``` function, with `random_state=0` to ensure consistent distribution across runs.

Since the data contains only two columns — one independent and one dependent — and shows a clear relationship, linear regression was chosen as the model. Using the ```fit``` function, the model was trained on the training dataset.

Once training was complete, I created the line equation based on the model's weights and intercept to assess how well it fits the data points, as shown in the following image.
![image](https://github.com/user-attachments/assets/a66e07f2-2a96-4062-87da-24bbe3927ee9)

## Model Evaluation
The model's accuracy on both the training and test sets was approximately 98%, which is expected given the simplicity and straightforward nature of the dataset—it may simply be capturing basic patterns. Additionally, the mean absolute error was calculated to be around 2.89, indicating that, on average, each predicted score could deviate by this amount.

## Web Application
I built a basic web application using Python's Streamlit framework. The model, previously saved with ```pickle```, is loaded by the app to predict scores based on user input. The predicted score is then returned as a response within the web application.

# Thanks for reading
