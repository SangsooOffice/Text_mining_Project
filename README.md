# Project Title
Prediction hate speech based on data about hate speech in Korean. This project was conducted during the Text Mining class in the first semester of 2023.

# Why I do this project?
The increasing trend of cyberbullying is undoubtedly a concern in today's digital age. This form of bullying can have serious consequences for victims, and can lead to emotional distress, anxiety, depression, and even suicidal thoughts. In addition, there is a communication problem in the rule-based filtering system, which is the most used now. So to solve these problems, we chose the topic of creating a hate expression filtering system based on language models.

# Project Process

**Dataset**
- We used datasets related to hate speech. [**git-hub**](https://github.com/smilegate-ai/korean_unsmile_dataset) , [**huggingface**](https://huggingface.co/datasets/jeanlee/kmhas_korean_hate_speech) , [**git-hub**](https://github.com/2runo/Curse-detection-data) , Comments on YouTube(Crawling)

**Preprocessing**
- Because it is labeled as a type of hate speech, it is re-encoded into binary form after looking at the label
- - For training, we set the ratio of train, validation, and test sets to 7:1:2. 

**Modeling**
- Fine-tuning a pre-trained model for the task of detecting hate speech.
- The initial learning rate is 5e-5/5e-6, and the optimizer used is Adam/AdamW.
- klue-BERT and klue-roBERTa used TensorFlow v2.
- KcBERT and KcElectra used PyTorch Lightning v2.

**Masking**
+ Stochastic Method

<img src = "https://github.com/user-attachments/assets/fb7b73f8-eb70-44fc-a7ed-7f2885d6157e" width = 100% height = 150></img>

+ LIME(XAI) Method

<img src = "https://github.com/user-attachments/assets/d44f5f4c-22af-4c74-bc2e-01b7f37c4eb3" width = 100% height = 150></img>

# Result
+ Modelling results showed that the klue-bert-based model performed best.

![image](https://github.com/user-attachments/assets/ef336756-8d6a-43b8-a3ce-21eaf0f27d8e)


+ I used an additional YouTube comment to see the generalization performance. Comparison model: [**Electra base**](https://github.com/JminJ/Bad_text_classifier) 

![image](https://github.com/user-attachments/assets/5f925d8c-0a49-4188-8bf4-d6b84ea0af38)

# contribution
- It is possible to accurately filter comments on SNS such as Twitter, Instagram, and YouTube.

- It is possible to mask expressions that may be inconvenient for users on anonymous conversation platforms of multiple ages such as KakaoTalk open chat.

- It guarantees freedom of expression in the range of news comments except for disparaging/deprecating/hating expressions of certain people.

- Since it is open-source, it is possible to perform filtering appropriate to the platform through additional learning of context suitable for a specific domain or additional learning of its own data.

# Difficult Point
- the part of a sentence that sets the hate expression threshold