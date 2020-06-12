# Document Analysis
Topic Models On Documents and Community Information.

This code looks through the narratives of the documents received in the Green lawsuit and performs preliminary topic modeling. It also takes the list of generated communities from the "Watts project" and adds additional information for further analysis.

Preliminary findings indicate that there are hidden themes in complaints that are not reflected in the categorization. This analysis is not meant to be final or indicative in any way. We used a Latent Dirichlet Allocation Topic Model for this analysis with a k-value of 15.

### Files to know in data/output:
* 'BigCommunityDataset.csv' - This is the dataset indexed by community with all the information needed for further analysis.
* 'documentAssignments.csv' - These are the topic probabilities for each document in the narratives file.
* 'officerCommAssignments.csv' - These are the community assignments for each officer.
* 'topic_interpretations.xlsx' - These are manually generated topic intepretations
* 'Topic_List' - These are the top 20 words for the 15 topics. This was used to generate manual topic labels.

Presentations contain information on the methodology employed as well as some helpful graphics.

### Below is a list of the variables in 'BigCommunityDataset.csv' and an explanation of how they were calculated:

* Community_ID: The numeric code that identifies a community. Officers that share a community ID are in the same community. 
* Count: Number of officers in community.
* Degree: Average degree of officers in community in social network of officers. Note: some edges were removed from network.
* Weighted.Degree: Average weighted degree of officers in community in social network of officers. See above note
* yearsOnForce: Average number of years on force of officers in community.
* current_age: Average age of officers in community.
* percentBlack: Percent of officers in community who are Black.
* percentWhite: Percent of officers in community who are White.
* percentMale: Percent of officers in community who are male.
* percentFemale: Percent of officers in community who are female.
* WithinCommunityComplaints: Number of complaints that listed more than one officer in the community.
* internalComplaintsPerPerson: Within Community Complaints divided by Count
* jaccardLabProp: Jaccard index for Louvain community detection and Label Propagation community detection. 1 is best.
* percentFlagged: Percent of officers in community who were of types 4 and 6. See Watts paper for further explanation.
* Index_Value: "Crew Probability" 1 indicates high chance of crew, 0 indicates little to no chance.
* DetectedCrew: Was this community identified as a crew?
* currentlyActive: How many officers in this crew are currently active
* NumberOfDocs2OrMoreListed: How many documents are there that list 2 or more officers
* AvgNumberOfDocs: NumberOfDocs2OrMoreListed divided by Count
* NumberOfDocRequests: Number of Document Requests by CPDP users.
* link: The pinboard link. Contains UIDs in this.
* numberOfDistinctSettlements: Number of settlements listing at least one officer in the community.
* TotalPayouts: Sum of the settlement amounts for each settlement listing at least one officer in the community
* UseOfForce_2orMore: Number of use of force complaints that list 2 or more officers.
* IllegalSearch_2orMore: Number of illegal search complaints that list 2 or more officers.
* FalseArrest_2orMore: Number of false arrest complaints that list 2 or more officers.
* OpsPersonnel_2orMore: Number of operations and personnel violation complaints that list 2 or more officers.
* CriminalMisconduct_2orMore: Number of criminal misconduct complaints that list 2 or more officers.
* VerbalAbuse_2orMore: Number of verbal abuse complaints that list 2 or more officers.
* NumberOfSustained_2orMore: Number of sustained complaints that list 2 or more officers.
* NumberOfNotSustained_2orMore: Number of not sustained complaints that list 2 or more officers.
* NumberOfNoAffidavit_2orMore: Number of no affidavit complaints that list 2 or more officers.
* NumberOfExonerated_2orMore: Number of exonerated complaints that list 2 or more officers.
* NumberOfUnfounded_2orMore: Number of unfounded complaints that list 2 or more officers.
* noActionTaken_2orMore: Number of complaints that list 2 or more officers resulting in no action.
* PenaltyNotServed_2orMore: Number of complaints that list 2 or more officers resulting in no penalty served.
* Resigned_2orMore: Number of complaints that list 2 or more officers resulting in resignation.
* Reprimand_2orMore: Number of complaints that list 2 or more officers resulting in a reprimand.
* AdministrativeTermination_2orMore: Number of complaints that list 2 or more officers resulting in administrative termination.
* Reinstated_2orMore: Number of complaints that list 2 or more officers resulting in reinstatement.
* Suspension_2orMore: Number of complaints that list 2 or more officers resulting in suspension.
* blackComplainants_2orMore: Number of Black complainants on complaints that list 2 or more officers.
* whiteComplainants_2orMore: Number of White complainants on complaints that list 2 or more officers.
* hispanicComplainants_2orMore: Number of Hispanic complainants on complaints that list 2 or more officers.
* maleComplainants_2orMore: Number of male complainants on complaints that list 2 or more officers.
* femaleComplainants_2orMore: Number of female complainants on complaints that list 2 or more officers.
* totalTRRs: Sum of TRRs of each officer. If two officers in a community are involved in the same TRR, it shows up as 2. This is true for all TRR variables.
* totalShotUnarmedVic: Total number of TRRs indicating that officers shot and hit an unarmed victim.
* totalTRRsWithFirearm: Total number of TRRs indicating that officers discharged a firearm.
* totalTRRsWithTasers: Total number of TRRs indicating that a taser was used.
* totalIncidentsShotFirearmOrTaserFirst: Total number of TRRs indicaating that the officer fired a taser/firearm first.
* totalBlackTRRVics: Total number of TRRs with Black victims.
* totalWhiteTRRVics: Total number of TRRs with White victims.
* totalHispanicTRRVics: Total number of TRRs with Hispanic victims.
* totalMaleTRRVics: Total number of TRRs with male victims.
* totalFemaleTRRVics: Total number of TRRs with female victims.
* averageTRRVicAge: Average age of TRR victims
* AvgTRRsPerOfficer: totalTRRs divided by Count
* AvgTRRsWithFirearmPerOfficer: totalTRRsWithFirearm divided by Count
* AvgTRRsWithTaserPerOfficer: totalTRRsWithTasers divided by Count
* ToRead_ordered: An ordered list of complaints to read based on topic analysis of the complaints with narrative information.
