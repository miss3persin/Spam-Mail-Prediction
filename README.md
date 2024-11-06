# Spam Mail Prediction Model

This project demonstrates a **Spam Mail Prediction** system using **Logistic Regression**. The model classifies emails as either **Spam** or **Ham (Not Spam)**, which can help in automatically filtering unwanted emails from a user's inbox.

---

## Overview  
This spam filter model is trained to recognize patterns in spam messages, enabling it to make accurate predictions on new messages. It uses **Natural Language Processing (NLP)** techniques, such as **label encoding** and **feature vectorization**, to process the text data before classification.

---

## Dataset Description  
The dataset consists of labeled messages, indicating whether each message is **Spam** or **Ham**. The dataset was preprocessed by encoding the labels and vectorizing the text data, which enhances the model's ability to understand the content in each message.

### Dataset Columns:
- **Category**: Indicates if the message is 'spam' or 'ham' (not spam).
- **Message**: The content of the email/message text.

#### Example:
| Category | Message |
|----------|---------|
| ham      | "Go until jurong point, crazy.. Available only ..." |
| spam     | "Free entry in 2 a wkly comp to win FA Cup fina..." |

### Preprocessing:
- **Label Encoding**: The **Category** column is encoded to numerical values: `spam = 1` and `ham = 0`.
- **Feature Vectorization**: The **Message** column is vectorized to convert text data into numerical features that the model can interpret.

---

## Model Performance
The model is trained on the processed data, achieving high accuracy in distinguishing between spam and ham messages, providing effective filtering for unwanted emails.

---

## Model Usage  

To use this model, pass in a new message to predict if it is **Spam** or **Ham**. Below is an example:

```python
# Example email message
X_new = ["URGENT! You have won a 1 week FREE membership in our £100,000 Prize Jackpot! Txt the word: CLAIM to No: 81010 T&C www.dbuk.net LCCLTD"]

# Transform the new message to match the training features
X_new_feature = feature_extraction.transform(X_new)

# Predict whether the email is spam or ham
prediction = model.predict(X_new_feature)

if prediction[0] == 1:
    print('This is a Spam Mail')
else:
    print('This is a Ham Mail')
```
