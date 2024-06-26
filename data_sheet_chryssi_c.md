# Datasheet Template

As far as you can, complete the model datasheet. If you have got the data from the internet, you may not have all the information you need, but make sure you include all the information you do have. 

## Motivation

- For what purpose was the dataset created? 
The datasets were created to study and project the impact of climate change, particularly focusing on the correlation between global temperatures, UK temperatures, and sea level rises. This is to understand the potential risks posed to assets due to climate change and to develop effective mitigation strategies.

- Who created the dataset (e.g., which team, research group) and on behalf of which entity (e.g., company, institution, organization)? Who funded the creation of the dataset?
The datasets were likely created by climate research institutions, possibly funded by governmental or international climate organizations. Specific creators might include teams from the MET Office.

 
## Composition

- What do the instances that comprise the dataset represent (e.g., documents, photos, people, countries)? 
The instances in the datasets represent monthly and annual temperature measurements (both median, lower, and upper bounds) for the UK and globally, as well as decadal sea level anomaly projections.

- How many instances of each type are there? 
UK Temperature Data: Monthly averages from 2050 to 2079.
Global Temperature Data: Monthly averages from 2040 to 2069.
Sea Level Data: Decadal projections from 2010 to 2100.

- Is there any missing data?
There are no explicit mentions of missing data in the provided datasets.

- Does the dataset contain data that might be considered confidential (e.g., data that is protected by legal privilege or by    doctor–patient confidentiality, data that includes the content of individuals’ non-public communications)?
No, the dataset does not contain any confidential data. It consists of publicly available climate data.

## Collection process

- How was the data acquired? 
The data was likely acquired through climate modeling and simulations, satellite observations, and historical climate records.

- If the data is a sample of a larger subset, what was the sampling strategy? 
The datasets appear to be projections and comprehensive records rather than samples.

- Over what time frame was the data collected?
The data spans different periods:

UK Temperature Data: 2050 to 2079
Global Temperature Data: 2040 to 2069
Sea Level Data: 2010 to 2100

## Preprocessing/cleaning/labelling

- Was any preprocessing/cleaning/labeling of the data done (e.g., discretization or bucketing, tokenization, part-of-speech tagging, SIFT feature extraction, removal of instances, processing of missing values)? If so, please provide a description. If not, you may skip the remaining questions in this section. 
The data have been preprocessed, cleaned and labelled to release to the public.
UK and Global temperature data were averaged to create annual averages from monthly values.
Sea level data were averaged across different scenarios to create a single average sea level anomaly for each decade.
Missing values were not explicitly mentioned, indicating they were likely handled during preprocessing.

- Was the “raw” data saved in addition to the preprocessed/cleaned/labeled data (e.g., to support unanticipated future uses)? 
 This information is not provided. It is advisable to save raw data for future use.

## Uses

- What other tasks could the dataset be used for? 
Long-term climate impact studies
Policy development and planning for climate change mitigation
Risk assessment for infrastructure purposes across the country
Educational purposes in climate science and environmental studies

- Is there anything about the composition of the dataset or the way it was collected and preprocessed/cleaned/labeled that might impact future uses? For example, is there anything that a dataset consumer might need to know to avoid uses that could result in unfair treatment of individuals or groups (e.g., stereotyping, quality of service issues) or other risks or harms (e.g., legal risks, financial harms)? If so, please provide a description. Is there anything a dataset consumer could do to mitigate these risks or harms? 

Limited data points for certain periods may affect the robustness of long-term forecasts.
The specific scenarios used for sea level projections could influence the results and should be considered.
The fields of the datasets could be standardised for better analysis of additional use cases.

- Are there tasks for which the dataset should not be used? If so, please provide a description.

## Distribution

- How has the dataset already been distributed? 
The datasets may be distributed through institutional repositories, governmental climate data portals, or academic publications

- Is it subject to any copyright or other intellectual property (IP) license, and/or under applicable terms of use (ToU)? 
The datasets are likely subject to terms of use and intellectual property rights held by the creators or funding organizations, such as the MET Office. 

## Maintenance

- Who maintains the dataset?
The datasets are maintained by the MET Office.

