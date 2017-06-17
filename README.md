# WikiLeaksDataset



The cables originated from U.S. Embassies and Consulates from around the globe, and are stored on the WikiLeaks web servers  in static HTML format, mixed and sorted by their dates of creation. By reorganizing these documents based on their geographic locations, we were able to create several distinct datasets of related cables – one per embassy. We then stripped the HTML tags, and categorized each of the paragraphs in terms of three fields: a UID consisting of sender, receiver, and time stamp; the raw text itself; and the classification label. We then divided classifications into three categories: Unclassified, Confidential, and Secret. In total, we created datasets from
the cables of four embassies: Baghdad, London, Berlin, and Damascus. We collectively refer to these datasets as the WikiLeaks Dataset. Statistics for each of the collected datasets in terms of document and paragraph classifications are in the following papers: 


```
@inproceedings{alzhrani2016automated,
  title={Automated big text security classification},
  author={Alzhrani, Khudran and Rudd, Ethan M and Boult, Terrance E and Chow, C Edward},
  booktitle={Intelligence and Security Informatics (ISI), 2016 IEEE Conference on},
  pages={103--108},
  year={2016},
  organization={IEEE}
}
```


```
@inproceedings{alzhrani2016automated,
  title={Automated big security text pruning and classification},
  author={Alzhrani, Khudran and Rudd, Ethan M and Chow, C Edward and Boult, Terrance E},
  booktitle={Big Data (Big Data), 2016 IEEE International Conference on},
  pages={3629--3637},
  year={2016},
  organization={IEEE}
}
```
```
@inproceedings{alzhrani2017automated,
  title={Automated US diplomatic cables security classification: Topic model pruning vs. classification based on clusters},
  author={Alzhrani, Khudran and Rudd, Ethan M and Chow, C Edward and Boult, Terrance E},
  booktitle={Technologies for Homeland Security (HST), 2017 IEEE International Symposium on},
  pages={1--6},
  year={2017},
  organization={IEEE}
}
```


# Format
The dataset is in Document-Term-Matrix csv format. We re-partitioned the dataset into training, validation, and test partitions.  The header is the feature set extracted from each partition. The paragraphs are converted to features matrix using the default values of CountVectorizer from sklearn.  


# Insights 
Each U.S diplomatic cable consisted of three sections. The first section is the head section, which includes some information regarding the sender and the receiver of the cable, cable security class, reference number and other information. The creation date of the cable is also included in the head section. We made sure when we created the dataset that we preserve the date, origin of the cable in the paragraph ID. Only the year and month of each cable is added to the paragraph ID. The cable itself has a label in the head section and its information sections or the paragraphs are also labeled. The cable label was in full words such as ”SECRET”, while the paragraph labels were between brackets in single capital letters such as ”S”. The document label is one of the entities that paragraph IDs consisted of. In addition to that, we kept the cable number and the paragraph position in the cable in the paragraph ID. The second section was the subject, and finally the third one was the body of the cable itself which included one more  paragraph

