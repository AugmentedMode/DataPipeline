# DataPipeline


#### Description

Implementation of a scalable distributed image stream processer using Kafka, Tensorflow, and Spark. 

This project will demostrate an ETL architecture which will:

1) Extract many traffic related images coming from multiple different sources (cars)
2) Transform each image into its predicted image embeddings based on OPENAI's CLIP model
3) Load all image embeddings into a database for it to be used for analytics (Image search using NLP)
4) Provide real-time analytics / reporting on our ETL 

#### Goals/Tasks

* Implement an end to end solution for a real world business case scenario within big data and computer vision
* Showcase the power of distributed processing within Big Data

##### Contributers

* Jacob Lebowitz