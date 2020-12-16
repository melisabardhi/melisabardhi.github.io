---
layout: post
title:      "Challenges in Machine Learning Applications"
date:       2020-12-14 07:30:23 -0500
permalink:  challenges_in_machine_learning
---


Machine Learning adoption is widespread across all industries. Its ability to perform specific tasks better than humans creates tremendous opportunity to improve economic productivity. The global machine learning market is projected to attain a Compounding Annual Growth Rate (CAGR) of 43% between 2020 and 2024, growing from $7.3b to $30.6b. As practitioners of ML applications, we are all incentivized to focus on the benefits of this technology in order to draw investment and resources.

However, I think we need to pause and introspect on it’s shortcomings just as much as we tout its benefits. Recognizing that Machine Learning can impact lives - on such a large scale and in such rapid speed - at the press of a button, we have a responsibility to make thoughtful decisions on its applications. After all, our children will live in this world we are creating.

As a student of Data Science, I am tremendously excited about its potential. However, the more I delve into the subject, the more I also recognize its deficiencies. I believe this is a good thing, and this is something all Data Scientists need to embrace more. We need to discuss the shortcomings of the models we build just as much as we espouse their benefits, to raise awareness and focus our resources towards building better, not necessarily more, artificial intelligence. In this blog, I’d like to broadly cover the use cases of Machine Learning, while also providing examples of where ML has gone wrong and the lessons we should learn from it.

**Anomaly Detection**
Successful anomaly detection hinges on an ability to accurately analyze time series data in real time. Time series data is typically a pair of two items: a timestamp for when a metric is measured, and the value associated with that metric. To detect outliers and spot anomalies real-time, a potential outlier is compared to peers, trends or a baseline.

Examples:
* Detecting the appearance of an anomoly on earth’s surface or atmosphere using satellite imagery
* IT performance monitoring on resource consumption (such as abnormal CPU usage, memory usage, spikes, high/low loads)
* Monitoring abnormal network traffic, such as traffic from unknown IP addresses or high volume to a specific host
* Banks identifying unusual transactions and requesting customer verification

Challenges: 
Anomalous data is scarce and hard to define, both being large obstacles in collecting enough training data to improve a model’s ability to identify true anomalies.


**Chatbot** 
Chatbots apply sophisticated Pattern Matching methods (i.e., Artificial Intelligence Markup Language (AIML), Natural Language Understanding, Natural Language Processing, Speech Recognition, or Sentiment Analysis) to understand user contents and needs and provide a suitable reply. Chatbots include an app layer, a database and APIs.

Examples:
* Virtual Assistants such as Eno, Google Assistant, Amazon Alexa, Baidu Xiaodu Voice Assistant, etc.
* Messaging apps such as Facebook Messenger and WeChat
* Individual organizations’ apps and websites such as Microsoft Xiaoice social chat bot

Challenges: 
Chatbots can be trained from biased historical data. Microsoft’s chatbot Tay was an experiment which learned from the people it interacted with on Twitter and the messaging apps Kik and GroupMe. Within 24 hours, it started making racist remarks.


**Classification** 
Classification categorizes a data instance into a similar group. It does this by training historical data with known labels, and then applying an algorithm to automatically find categories for new data. In order to best map examples of input data to specific class labels, the training dataset must be sufficiently representative of the problem and have many examples of each class label, especially the minority.

Examples:
* Image classification for disease diagnosis in healthcare
* Text classification
* Sentimental Analysis on customer feedbacks, surveys, etc.

Challenges: 
One of the primary concerns with classification is that the sample of data may not be adequately representative by not ascribing enough importance to minority cases. Amazon tried building an artificial-intelligence tool to help with recruiting, but it showed a bias against women. Engineers found the AI was unfavorable toward female candidates because it had combed through male-dominated résumés to accrue its data.


**Computer Vision** 
Computer Vision extracts information from images and recognizes specific concepts. It can therefore perform a variety of tasks such as recognizing faces, characters in an image, detecting the location of an object in an image, or classifying images. It does this by learning from a visual database that has been annotated manually depending on the type of information it wants to extract, and then running new images through a neural network composed of successive layers of neurons which associate the new image to familiar images.

Examples:
* Application of facial recognition in scenarios of registration, authorized login, surveillance etc.
* Measuring headcount or statistics on attendance
* Analyzing displayed emotion, or attention

Challenges: 
Image factors like illumination, occlusion or low resolution, among others can limit the potential of facial recognition to work optimally. In Michigan, a faulty facial recognition match led to a man’s arrest for a crime he did not commit. There have been several cases in the US where an algorithm-based bot has accidentally identified a regular citizen as a criminal and has automatically suspended the driving license. Similar cases have also occurred at airports all over the world, where innocent people have been “recognized” as terrorists. In another case, a Tesla engaged in autopilot mode collided with a tractor-trailer, due to its inability to quickly distinguish the color between the background sky and vehicle.


**Recommendation Systems** 
Recommendation systems use history and preferences to predict what users like. The recommendation function takes information about the user such as demographics, preferences and behavior (inferred through clicks, views and purchases) to predict the rating that user might assign to a product. It also measures user and product similarity to drive similar recommendations.

Examples:
* Advertisements when surfing a website
* Posts on social media
* Recommended videos on Youtube, movies on Netflix or courses on Safaribooks

Challenges: 
The less data a recommendation system has about a user, the more likely it is to incorrectly assume their preferences. We have all been recommended content which is not personalized to us but simply the most popular.


**Segmentation**
Segmentation splits data into different clusters based on shared characteristics. Clustering uses algorithms to identify how different types of data are related and creates new segments when appropriate. Similarity between data is determined through distance measurements.

Examples:
* Using deep learning for biomedical image processing of radiography, thermography, ultrasound, nuclear medicine and CT to identify patterns, diseases etc.
* Segmenting businesses based on industry, location, number of employees, products, annual profit, etc.
* Using targeted marketing on customers separated based on behavior, demographic information, lifestyle, etc.

Challenges: 
Due to both the lack of examples in biomedical image processing and complexity of images studied, segmentation can be incorrect and wrongly diagnose a patient. The classification of biomedical images almost always has to be verified by a certified professional after being segmented by AI.


The gravity of a single mistake in these applications varies. In cases where human lives are involved - arresting someone, identifying a terrorist, diagnosing a disease - ethical treatment of data and accurate results are of utmost importance. As AI increases its capabilities, we must ensure proper checks , diverse data, and ethical standards for research.

