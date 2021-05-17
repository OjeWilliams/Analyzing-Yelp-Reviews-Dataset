# **Analyzing Yelp Reviews Dataset**
- [**Analyzing Yelp Reviews Dataset**](#analyzing-yelp-reviews-dataset)
    - [Background](#background)
    - [Setting up the Project](#setting-up-the-project)
      - [Part I: Installation and Inital Setup](#part-i-installation-and-inital-setup)
      - [Part II: Analyzing Categories](#part-ii-analyzing-categories)
      - [Part III: Do Yelp Reviews Skew Negative?](#part-iii-do-yelp-reviews-skew-negative)
      - [Part IV: Can the Elites be trusted?](#part-iv-can-the-elites-be-trusted)

 
 ### Background
 
 This project involves diving into a dataset of [Yelp](https://www.kaggle.com/yelp-dataset/yelp-dataset) reviews and seeing what interesting things we can find. The dataset is a collection of Yelp's reviews, user data and businesses across 8 metropolitan areas in the USA and Canada. The dataset is quite large (11gb) and to investigate it we will leverage a Spark Cluster on AWS EMR  for loading the data as well as an S3 bucket for uploading the data while all analysis will be completed using a Jupyter Notebook. 

  


 ### Setting up the Project

 #### Part I: Installation and Inital Setup 
1. Upload all of the necessary Yelp Json files into a AWS S3 bucket so that it can be accessed by EMR as seen below: 
   
![](https://github.com/OjeWilliams/Analyzing-Yelp-Reviews-Dataset/blob/main/images/s3_bucket.png)
<br />
<br />

2. Provision an Spark Cluster on EMR. Ensure that you go to Advanced Options and select the following :

   - Step 1: Software Configuration: Realease: emr-5.31.0
       - Hadoop 2.10.1
       - Hive 2.3.7
       - Hue 4.7.1
       - Spark 2.4.6
       - Livy 0.7.0
    -   Step 2: Hardware : make sure EC2 Subset is configured correctly that instance types are m5.xlarge


![](cluster_configuration.png)  &nbsp; <br />
   
3. Create a Jupyter Notebook for all analysis

![](notebook_configuration.png)


4. Install all of the necessary libraries as well as load your data from your S3 bucket as a pyspark dataframe. Also ensure that you change the following:
    - Kernel --> Change Kernel --> Pyspark

<br />
<br />
<br />

  

#### Part II: Analyzing Categories
In this part we will attempt to denormalize the data categories aligned with each business to increase efficiency and then carryout some simple analysis on the result. 

   <br />
  

#### Part III: Do Yelp Reviews Skew Negative?
In this part we investigate the skew of the yelp reviews and also check for normality.

   <br />

#### Part IV: Can the Elites be trusted?
In this part we investigate if elite yelp reviews(star) ratings can be trusted?
