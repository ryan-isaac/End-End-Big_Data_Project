# Defi Big Data Project

The uploaded file includes the PowerPoint presentation that presents the model used for this end-to-end project.  

## Introduction:
The projects aim to collect primary data from Twitter that are related to Defi. Defi refers to decentralized finance, a relatively new term in the financial markets that has gained increased popularity since the COVID-19 pandemic started globally at the end of 2018.  This project is focusing on sentiment analysis to have a better understanding of what the people think of it and how positive/negative their tweets are about it using cloud services. It gained its popularity firs in 2017, where crypto currencies or digital currencies prices skyrocketed.
Secondary data suggests that the number of blockchain wallets increased along with the total USD amount locked in defi.  It is also observed that the value of crypto currencies is increasing compared to the US dollar where its value was in a continuous decline compared to international currencies and most importantly, compared to Bitcoin (The most valuable and dominant digital currency).
There are several reasons why I selected this as a topic to analyze.  The crypto currency market has a huge market opportunity as it is easily accessed from anywhere in the world using the web. Recently Kraken -a crypto exchange- became a bank officially, and many banks has become accepting of the new financial technologies and digital currencies. Moreover, and most importantly, investors are seeing great opportunities in Defi. The first large corporation that invested heavily in Bitcoin was MicroStrategy.  It received a lot of criticism, yet it could be an incentive for others to investigate the untapped opportunities of this market.

## Goals:
This project uses a sentiment analysis model to answer 3 main questions:
1- Is the sentiment positive about Defi?
2- Who are the major influencers tweeting about Defi?
3- Where are most tweets coming from?

## Approach:
The data was collected over a short period of time using AWS EC2 instance. It was controlled through Gitbash using Linus commands. Two main tools were used in python3, Boto3, and Twitter API.  It was downloaded on AWS and then left to collect the live data automatically.  The data was saved in json format in AWS S3 bucket, using AWS Kinesis Firehose with a setting of writing the data every 5 minutes or when the data size reaches 5 MB. The data in AWS S3 was connected to two sides, one for the visualization, and another for the processing, data engineering, and sentiment analysis.
In the processing end, the data was connected to DataBricks to use Apache Spark to run the model on it.  The sentiment analysis model was pre trained on another data and was ready to pass the data through.  Using some Scala, Pyspark, and SQL syntaxes, the data manipulation was done then passed through the model to generate the sentiment columns. The new data frame generated through this process is sent back to AWS S3 bucket where it was connected to Amazon Athena where a schema was set to contain the data frame and connect it to AWS Quicksight for the visualization dashboard.
### Security
The channels used were set to accept my own IP Address, preventing any unauthorized access to the data. Additionally, AWS policies were set to allow specific access for certain services on user and bucket level.

## Conclusion:
- The sentiment was only 15% positive
- Major Influencers:
  DefiWhale (Number of Tweets)
  Binance (Number of Followers)
- Top Locations:
  “None”
  Crypto Ocean
  Indonesia
  
It appears that the data collected was biased given the period it was collected in.  The market was not performing well, which might have been the reason for the low sentiment. Additionally, the sentiment analysis model might not be the best option in this case, since it was pre trained on labels related to different data.  Having the knowledge on how to build this pipeline and manipulate the data will allow future opportunities for improvement. However, the project is performed for demonstration purposes and thus, not further tunning will be done.
Snapshots of the dashboard and some of the coding used is available in the PowerPoint file.

