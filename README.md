# Udacity Data Science Nanodegree - Capstone Project 
This Repository contains the files for Udacity's Data Science Nanodegree Capstone Project.

### 1. Motivation  
Customer acquisition is costly. In the digital age it makes little difference whether you send an email to one or to a thousand people, but those who consider email to be spam will quickly become annoyed by it. So it would be an advantage to know before sending the email if the recipient is interested in the offer sent to him. With the help of supervised and unsupervised learning techniques, this project is intended to explore this possibility. 

### 2. Installations
- [Python 3.X](https://www.python.org/downloads/)
- [Numpy](https://pypi.org/project/numpy/)
- [Pandas](https://pypi.org/project/pandas/)
- [Matplotlib](https://pypi.org/project/matplotlib/)
- [scikit-learn](https://pypi.org/project/scikit-learn/)
- [kmodes](https://pypi.org/project/kmodes/)

### 3. File Descriptions
- **BlogPost.md**: A blog post about my finding
- **Arvato Project Workbook.ipynb**: A Jupyter Notebook that keeps my calculations and results

### 4. Findings
- With 41 features an AUC score between 0.55 and 0.65 can be achieved
- Random forest classifier has with 41 features a higher AUC than with 107. This is probably due to the fact that filling the *NAs* with the Random forest mode is more confusing than helpful. 
- The costs of *k-modes* are very volatile. it is therefore advisable to run it several times to find a stable solution.

### 5. Acknowledgements
Thanks to bertelsmann Arvato for providing the data sets and the survey participants.
