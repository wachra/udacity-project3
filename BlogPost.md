# Know your customers before they know you
![Grafik1](https://images.squarespace-cdn.com/content/v1/5e40a797e62a4b50541a9405/1581297196838-KON9VPC26PSPT3XMMKLE/ke17ZwdGBToddI8pDm48kMD5Pqg4EOtnvApb2o-QJb97gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z5QPOohDIaIeljMHgDF5CVlOqpeNLcJ80NK65_fV7S1UfM-vp47RsIPAhXUQB0PfEDPb1hR5DcDamr0q3NgByRy7zs2yPjc1ECvpa5Zm_kMqw/ca.png)

## Introduction
Customer acquisition is costly. In the digital age it makes little difference whether you send an email to one or to a thousand people, but those who consider email to be spam will quickly become annoyed by it. So it would be an advantage to know before sending the email if the recipient is interested in the offer sent to him. With the help of supervised and unsupervised learning techniques, this blog post - representing my capstone project of the Udacity Nanodegree - is intended to explore this possibility.   

In order to achieve these goals, I took the following steps:
- Exploration of the given data
- Data preprocessing to reduce the number of columns with a lot of *NAs*
- Using k-modes, demographics data for the general population of Germany and customer data is clustered and compared with each other  
- Using random forest classification (including hyperparameter optimization and cross-validation), a prediction is made on the test data set as to how likely it is that a person will respond
- The prediction was uploaded to [Kaggle](https://www.kaggle.com/) and evaluated using the metric *AUC (Area Under the Curve)* 


## Data
The author had access to four data sets that originated from the cooperation between *Udacity* and *Bertelsmann Arvato*:
1. Demographics data for the general population of Germany
2. Demographics data for customers of a mail-order company
3. Demographics train data for individuals who were targets of a marketing campaign
4. Demographics test data for individuals who were targets of a marketing campaign

The first two sets of data serve to compare the (german) customers of a mail-order company with the population of Germany. Since there was no label for any of the two data sets, an unsupervised procedure (k-modes) was used in the next but one chapter. It was noticeable that 10% of the data was missing from the first data set and about 20% from the second. For the third dataset, however, the author had labels so that he could use a supervised learning procedure *(random forest classification)*. With this trained model, predictions were then made on the fourth dataset - the test dataset.  
The records all had at least 350 similar columns. These contained information about the age, social status or children of the different persons.

## Preprocessing
Before the similarity of the first two data sets can be determined with k-modes, the columns were checked for missing values *(NAs)*. As the following graphic shows, the majority of the first data record has a percentage of *NAs* less than or equal to 20%. 

![Grafik2](https://i.imgur.com/XG4QP2z.png)  

It was remarkable that negative values were entered in many categorical columns. On closer inspection, it was discovered that this was an encoding for *NAs*. After these values were also provided as NAs, the author decided to remove columns with a share of 20% of missing values. This step was necessary because k-modes do not allow missing values and some supervised procedures have problems dealing with missing values. This step is necessary because k-modes does not allow missing values and also some supervised procedures have problems dealing with missing values. Since the remaining columns were all categorical, the missing values were replaced with the mode.

## Unsupervised Learning: k-modes
To be able to compare the first two datasets with each other, a cluster method is required, which does not presuppose metric scaling of the columns: [k-modes](https://github.com/nicodv/kmodes). Instead of calculating the distance of the vectors to each other, the number of different values - compared to the centroid - are counted. The centroid represents the mode of the observations assigned to it. The observations are assigned to the centroid to which the observations show the least deviation. 

![Grafik3](https://i.imgur.com/Q5x6Dpj.png)  

The graph above compares the percentage distribution of persons in the two data sets for a k-mode with 7 clusters. Except for cluster 2 and 6, the percentage of persons is almost equal. A closer look reveals that cluster 6 in column 15 (`D19_VERSAND_ANZ_24`) shows anomalies - compared to the other clusters - and cluster 2 in columns 2, 17, 31 and 39 (`SEMIO_SOZ, ZABEOTYP, ANREDE_KZ` and `FINANZ_MINIMALIST`).   

## Supervised Learning: Random Forest Classifier
Finally, it will be investigated whether the number of users on Stackoverflow in European non-English speaking countries depends on their knowledge of English. The ten countries with the absolute number of participants were used for this purpose. To ensure comparability between the countries, the number of participants in each country was set in relation to the number of inhabitants. The English level of the respective countries was taken from [this](https://www.ef.com/wwen/epi/) website.  

![Grafik4](https://i.imgur.com/uB1ZCz3.png)  
![Grafik5](https://i.imgur.com/AvR9mFm.png)
As can be seen, the number of users from countries whose English skills are considered higher is more frequent (in relation to the respective number of inhabitants). One could conclude from this that the information on Stackoverflow is not accessible to those whose English skills are considered lower. Improving school education or integrating a translator into Stackoverflow could be actions to address this issue.   

*Assumption: The author assumes that the number of study participants per country is proportional to the number of Stackoverflow visitors who did not participate in the study. Furthermore, he assumes that the availability of the internet is the same in all 10 countries compared and that the share of developers in each country is the same.*


## Conclusion
In this article, we took a look at the 2014 and 2019 survey data to get an insight into the user base of Stackoverflow. 

1. *Python* and *Javascript* are the most rapidly growing programming languages.
2. Older developers work from home more often than younger ones.
3. The better the English level in a country, the higher the probability they will visit Stackoverflow


#### Sources
- https://images.squarespace-cdn.com/content/v1/5e40a797e62a4b50541a9405/1581297196838-KON9VPC26PSPT3XMMKLE/ke17ZwdGBToddI8pDm48kMD5Pqg4EOtnvApb2o-QJb97gQa3H78H3Y0txjaiv_0fDoOvxcdMmMKkDsyUqMSsMWxHk725yiiHCCLfrh8O1z5QPOohDIaIeljMHgDF5CVlOqpeNLcJ80NK65_fV7S1UfM-vp47RsIPAhXUQB0PfEDPb1hR5DcDamr0q3NgByRy7zs2yPjc1ECvpa5Zm_kMqw/ca.png
