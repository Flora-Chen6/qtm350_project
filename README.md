# QTM 350 Final Project

## Introduction
Email is the most widely used communication platform for professionals and college students, with 85% of professionals using email regularly for work and 87% of students using it for academic purposes. However, emails can be easily misconstrued, especially regarding sentiments and tones. This ambiguity in emails can be more challenging for recipients from different cultural backgrounds. Additionally, senders may send text-dense emails that make it difficult for the recipient to comprehend the key points. Fortunately, AWS provides Amazon Comprehend, which can help detect valuable insights and connections in text using machine learning. Therefore, the project aims to use AWS’ Amazon Comprehend service to test three features on sentences from emails to extract key sentiments and entities: **Entity Recognition, Sentiment Analysis**, and **Targeted Sentiment Analysis**. 

### What is Amazon Comprehend
Amazon Comprehend is a natural language processing (NLP) service provided by AWS. It uses machine learning algorithms to extract insights and relationships from text data, such as social media posts, customer reviews, and news articles. It can perform a range of NLP tasks including: Detecting the dominant language, Detecting named entities, Detecting key phrases, Determining sentiment, Analysis for targeted sentiment, Detecting syntax, Async analysis for event detection, Async analysis for topic modeling. 
[A walk-through tutorial](https://github.com/Flora-Chen6/qtm350_project/blob/main/Amazon-Comprehend-Tutorial.ipynb) to use Amazon Comprehend APIs on AWS CLI is provided to be followed along.

## Methods
We put forward hypothesis to investigate and test the performance and accuracy of the three features of Amazon Comprehend. 
Hypothesis 1: Entity Recognition will struggle to detect all entities within a sentence byt will have moderate to strong performance on accurately classifying entities. 
Hypothesis 2: Sentiment Analysis will be able to correctly identify the overall sentiment of sentences and whole emails but the confidence score might vary from the expected confidence score. 
Hypothesis 3: Targeted Sentiment Analysis will be able to accurately detect the sentiment of specific entities mentioned in a given sentence, even though the sentiment of the overall sentence might be different from the sentiment of specific entities within the sentence.

#### Design/Architecture
The architecture diagram below shows the specific steps of the architecture. We first store all of our input text data into a S3 bucket. Then we initiate a notebook instance in Sagemaker. By calling the bucket, we pass the data stored in the bucket into Amazon Comprehend, which we output for our following analysis. In the end, we pushed our analysis and results to a GitHub repository. 
<img src="https://github.com/Flora-Chen6/qtm350_project/blob/main/architectural.png" width=60% height=60%>

### Data Preparation and Collection
To test effectiveness of Amazon Comprehend on correctly identifying entities and sentiments of emails, all group members collect sentences and paragraphs of real-life data sent under professional setting. We choose the texts under different topics and with different lengths to better test the performance of Amazon Comprehend under different circumstances. 


## Results

### Entity Recognition
The AWS text recognition system struggles to identify a sufficient number of entities in our sentences, as shown by a 27% identification rate. Even when it correctly identifies entities, the overall average performance is only 18% due to the low correct entity identification proportion. In particular, jargon and lexicon-dense sentences with important information may not be suitable for the system. Moreover, the limited hierarchy of entity types, including the vague "OTHER" category where most lexicons are placed, makes it unsuitable for identifying and classifying nouns in sentences full of diverse terminology. Thus, we do not recommend using AWS entity recognition for emails containing similar sentences to the email sentences we inputted. 

### Sentiment Analysis
The sentiment analysis function did not perform well on both types of texts. The accuracy was higher for whole emails, possibly because more context was given to aid understanding. However, the results were limited by the small sample size and variations among the group members' labelings due to personal experiences which could explain the difference in accuracy between expected and actual results. If this function is to be used, we highlight the need for caution when interpreting sentiment analysis results and the importance of considering the data's context and limitations.

### Targeted Sentiment Analysis
Targeted Sentiment generally has a low accuracy. It does a better job identifying neutral sentiment than it does for positive or negaive sentiments. However, it performed better when analyzing individual entities separately instead of the whole sentence compared to Sentiment Analysis. 

## Conclusion
We acknowledge the limitations of our research, particularly the small size of our dataset, which could affect the reliability of our findings. In the future, it may be worth exploring AWS Comprehend's performance on different sources such as social media posts and newspapers, and comparing its performance on various text sources. Moreover, researchers could also investigate AWS Comprehend's performance in different languages besides English.

You can access our webpage through the [link](https://myawsbucket-groupproject.s3.amazonaws.com/Amazon_Comprehend_Blog+(1).html).
