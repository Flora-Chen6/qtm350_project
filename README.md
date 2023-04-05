# QTM350 Final Project

## Introduction
Automated text extraction and comprehension are attractive to different interest groups because these methods can digest thousands of different online text sources at once to track adjusting attitudes to specific changes. However, due to the subjectivity of textual human speech, machines have traditionally failed to understand nuanced human terminology. With growing demands to analyze text more automatically, we seek to test Amazon Comprehend advertising this capability. We aim to see how this service works and if it may be a reliable tool for accurately digesting complex and subjective human speech.

### What is Amazon Comprehend
Amazon Comprehend is a natural language processing (NLP) service provided by AWS. It uses machine learning algorithms to extract insights and relationships from text data, such as social media posts, customer reviews, and news articles. It can perform a range of NLP tasks including: Detecting the dominant language, Detecting named entities, Detecting key phrases, Determining sentiment, Analysis for targeted sentiment, Detecting syntax, Async analysis for event detection, Async analysis for topic modeling. 
[A walk-through tutorial](https://github.com/Flora-Chen6/qtm350_project/blob/main/Comprehend-Tutorial.ipynb) to use Amazon Comprehend APIs on AWS CLI is provided to be followed along.

## Methods
We put forward hypothesis to investigate and test the performance and accuracy of four functionalities of Amazon Comprehend: dominant language detection, sentiment analysis, entity recognition, and topic modeling.

#### Design/Architecture
The diagram illustrates the overall outline of what AWS services were utilized in this architecture.
<img src="https://github.com/Flora-Chen6/qtm350_project/blob/main/architecture.png" width=60% height=60%>

### Data Preparation and Collection
To ensure diversity of the data and the effectiveness of different hypothesis testing, we generate and collect data from a variety of sources, including our own generation, auto-translation tool, reviews/comments online. By providing a wide range of data, we aim to test the accuracy of Amazon Comprehend and identify its performance under different circumstances.
