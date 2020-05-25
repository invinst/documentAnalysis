# Document Analysis
Topic Models On Documents

This code looks through the narratives of the documents received in the Green lawsuit and performs preliminary topic modeling. 

Preliminary findings indicate that there are hidden themes in complaints that are not reflected in the categorization. This analysis is not meant to be final or indicative in any way. We used a Latent Dirichlet Allocation Topic Model for this analysis with a k-value of 15.

files to know in data/output:
* 'BigCommunityDataset.csv' - This is the dataset indexed by community with all the information needed for further analysis.
* 'documentAssignments.csv' - These are the topic probabilities for each document in the narratives file.
* 'officerCommAssignments.csv' - These are the community assignments for each officer.
* 'topic_interpretations.xlsx' - These are manually generated topic intepretations
* 'Topic_List' - These are the top 20 words for the 15 topics. This was used to generate manual topic labels.

Presentations contain information on the methodology employed as well as some helpful graphics.
