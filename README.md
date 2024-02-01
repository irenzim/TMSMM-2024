# Analysis of Russian Constitutional Court Proceedings

## What is this project about?

Over the past years, the development of Machine Learning and Artificial Intelligence has brought more attention to quantitative methods for the analysis of text data in the field of law. The applications of text mining can present various objectives and uses: those are implemented both as supervised methods (e.g., to make predictions of judiciary decisions as discussed by Medvedeva et al. 2019) and unsupervised, to conduct a historical analysis of the available corpus of legal documents. 

This case study is inspired by the paper of Wendel et al. 2022, implementing a topic modeling approach to proceedings of the German Constitutional Court. More specifically, the aim of the exercise is to delve deeper into the caveats and techniques of processing Russian legal lexicon and attempt to grasp a preliminary image of available data.

---
**Wendel, L., Shadrova, A., & Tischbirek, A. (2022).** From Modeled Topics to Areas of Law: A Comparative Analysis of Types of Proceedings in the German Federal Constitutional Court. German Law Journal, 23(4), 493–531. doi:10.1017/glj.2022.39

**Medvedeva, M., Vols, M., & Wieling, M. (2020).** Using machine learning to predict decisions of the European Court of Human Rights. Artificial Intelligence and Law, 28, 237-266.

## Legal introduction

**The Constitutional Court of the Russian Federation** (рус. Конституционный Суд Российской Федерации) is a high court within the judiciary of Russia that is empowered to rule on whether certain laws or presidential decrees are in fact contrary to the Constitution of Russia. Its objective is to protect the Constitution and support the population in terms of explaining the meaning of legal acts.

The Court consists of 11 judges, one being the Chairman (currently Valery Zorkin) and another one being Deputy Chairman. The Chairman is responsible for the allocation of cases to chambers, has considerable powers in the matters of appointment, and makes the initial recommendation for disciplinary measures, in particular dismissal.

Source: https://en.wikipedia.org/wiki/Constitutional_Court_of_Russia

## Data 

The dataset used can be downloaded from Kaggle: 
https://www.kaggle.com/datasets/athugodage/russian-legal-text-parallel-corpus

The authors of the dataset retrieved texts from the website Rossiyskaya Gazeta. It's a Russian newspaper published by the Government of Russia. The daily newspaper serves as the official government gazette of the Government of the Russian Federation, publishing government-related affairs such as official decrees, statements and documents. of state bodies, the promulgation of newly approved laws, Presidential decrees, and government announcements.
If there is any new proceeding published by the Constitutional Court, Rossiyskaya Gazeta provides descriptions or "comments" for the public, which serve as a simplified explanation of the documents. 

The dataset contains documents from **December 31, 2008 up to November 28, 2022** - 2963 records in total.

## Implemeted techniques

- Topic Modelling with Latent Dirichlet Allocation
- Fitting own Embedding Model on the Corpus with Gensim library 
- Named Entity Recognition: retrieved new features from texts: the identities of persons, organisations and locations (e.g. regions or countries) mentioned in newspaper's comments

## Python libraries 

This work was performed with the use of Scikit Learn LDA module `sklearn.lda.models` for topic modelling, `gensim` and `navec` for embeddings and `natasha` as a framework for extracting named objects as additional features. 

`navec` and `natasha` are the go-to libraries if you ever want to work with Russian. You can find detailed documentation here: 
https://github.com/natasha/natasha  
https://github.com/natasha/navec


