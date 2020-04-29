# Know your customers before they know you
![Grafik1](https://i.imgur.com/cpbk9DL.png)

## Introduction
Customer acquisition is costly. In the digital age it makes little difference whether you send an email to one or to a thousand people, but those who consider email to be spam will quickly become annoyed by it. So it would be an advantage to know before sending the email if the recipient is interested in the offer sent to him. With the help of supervised and unsupervised learning, this blog post is intended to explore this possibility for Bertelsmann Arvato.

## Data
The author had four data sets at his disposal:
1. Demographics data for the general population of Germany
2. Demographics data for customers of a mail-order company
3. Demographics train data for individuals who were targets of a marketing campaign
4. Demographics test data for individuals who were targets of a marketing campaign

The first two sets of data serve to compare the (german) customers of a mail-order company with the population of Germany. 

## Preprocessing
![Grafik2](https://i.imgur.com/Z2OQZBy.png)  

It is obvious that the languages *Python* and *Javascript* have gained significantly in popularity among Stackoverflow users over the last five years with an increase of 18.7% and 8.9% respectively. Among the losers are the programming languages *C#* and *Objective C*, which have a minus of 6% and 5.7%. So if you are looking for a seminal programming language for the next few years, *Python* or *Javascript* may your best bet.  

*Note: The surveys of 2014 and 2019 differ considerably in terms of questions and answer possibilities. Since the 2014 survey used the 11 programming languages listed here as the answer choice, these were also only compared with the values from 2019.*

## Do experienced developers tend to work from home and how has this changed over the last 5 years?
In times of COVID-19 many companies rely on home work of their employees. But how high was this rate before that time and has it changed within the last five years? Furthermore it shall be investigated whether there are differences regarding age. For example, one might think that experienced developers tend to work from home because their boss has known them longer or they have family to look after in parallel to their work. 

![Grafik3](https://i.imgur.com/NXf3m87.png)  

The graph shows that the share of people under thirty who do not rely on distance work is actually higher than for older people. The proportion of those who work almost exclusively at a distance also appears to increase with age, with the exception of those under 20 years of age. It is interesting to note that a polarizing effect has been observed over the last five years. The number of those who either never or work completely at a remote location has increased.   

## Is Stackoverflow less used in European countries where the percentage of English language skills is considered lower?
Finally, it will be investigated whether the number of users on Stackoverflow in European non-English speaking countries depends on their knowledge of English. The ten countries with the absolute number of participants were used for this purpose. To ensure comparability between the countries, the number of participants in each country was set in relation to the number of inhabitants. The English level of the respective countries was taken from [this](https://www.ef.com/wwen/epi/) website.  

![Grafik4](https://i.imgur.com/8aQ70EM.png)  

As can be seen, the number of users from countries whose English skills are considered higher is more frequent (in relation to the respective number of inhabitants). One could conclude from this that the information on Stackoverflow is not accessible to those whose English skills are considered lower. Improving school education or integrating a translator into Stackoverflow could be actions to address this issue.   

*Assumption: The author assumes that the number of study participants per country is proportional to the number of Stackoverflow visitors who did not participate in the study. Furthermore, he assumes that the availability of the internet is the same in all 10 countries compared and that the share of developers in each country is the same.*


## Conclusion
In this article, we took a look at the 2014 and 2019 survey data to get an insight into the user base of Stackoverflow. 

1. *Python* and *Javascript* are the most rapidly growing programming languages.
2. Older developers work from home more often than younger ones.
3. The better the English level in a country, the higher the probability they will visit Stackoverflow


#### Sources
- https://convertiblesolutions.com/wp-content/uploads/2015/03/Magnet.jpg
