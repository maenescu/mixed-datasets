<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

# Mixed Datasets

Final project for the Building AI course

## Summary
Mixed datasets contain both personal and non-personal data. My idea is to build an AI algorithm that is able to accurately label personal and non-personal data and sort them in two different categories, where possible. Where they are intrinsically linked, the algorithm would label personal/ non-personal data and anonymize the personal data from the dataset. This would allow to identify the applicable legal regime to each dataset (containing personal data vs. non-personal data).


## Background

Which problems does your idea solve? How common or frequent is this problem? What is your personal motivation? Why is this topic important or interesting?

Mixed datasets contain both personal and non-personal data. Non-personal data is data which originally did not relate to an identified or identifiable natural person, OR data which were initially personal data, but were later made anonymous. If non-personal data can be related to an individual in any way, the data must be considered as personal data.
If the two categories cannot be splitted (they are "intrinsically linked"), then the data protection requirements (GDPR for example) apply to the entire dataset as a whole. This leads to the following problems:

* Additional burdens on companies processing this sort of mixed datasets (such as compliance costs).
* It impedes the free flow of non-personal data, as the requirements for the flow of personal data are much stricter.
* It makes research, testing and training of AI models more difficult, because of the stricter requirements in terms of personal data processing (you cannot freely feed this data into the system, you must have a legal basis, such as the consent of the natural personal, for instance).
* These mixed datasets have stricter requirements in terms of data transfers to other countries (outside of the EU) if they contain personal data.

A few examples of mixed datasets, in which the personal and non-personal data are "intrinsically linked":
* a research institution’s anonymized statistical data and the raw data initially collected
* a company's tax records, mentioning the name and telephone number of the managing director of the company
* a company's knowledge of IT problems and solutions based on individual incident reports

My motivation in proposing this solution is to encourage the free flow of non-personal data without the restrictions linked to the processing of personal data, since this does not involve any risks for the individuals. By "free flow" of non-personal data I understand using this data for research, testing and training of AI models, sharing this data with other developpers, data scientists, researchers etc. This would allow for better and faster technological advancements and innovation, without posing the individuals' rights at risk, especially their right to privacy.

I believe this is an important topic because we are living in a data-driven world and we should take advantage and leverage all the potential of the non-personal data uses, especially towards innovation. By being obliged to apply personal data requirements to a dataset that contains both personal and non-personal data (regardless of the quantity of data in each category), the innovation process is slowed down.

## How is it used?

Describe the process of using the solution. In what kind situations is the solution needed (environment, time, etc.)? Who are the users, what kinds of needs should be taken into account?

Step 1. Train the algorithm to distinguish between personal and non-personal data from a dataset and to label the data accordingly.
Step 2. If the data are intrinsically linked => label the data as personal/non-personal and anonymize the personal data from the dataset. Once the data has been anonymized, the legal data protection requirements no longer apply, so the entire dataset becomes a non-personal dataset.
If the data can be splitted => label the data as personal/ non-personal and divide it into 2 different datasets. This would allow for the application of the data protection legal requirements only to the personal dataset, enabling easy data flow of the non-personal dataset.
Step 3. Constantly monitor the output of the system and feed back the results in order to increase the accuracy of the labling mechanism over time.

To be taken into account:
* In some cases, it is not desirable (or even legal) to separate personal from non-personal data in a given mixed dataset.
*  Example 1. Tax declarations of a company - in most countries, the law requires it to include the name and other personal identifiers of a legal representative of the company. In this case, the personal data (the data of the legal representative) cannot be separated from the non-personal data (tax data and other identifiers of the company);
*  Example 2. Copyrights. In this case, separating the personal data (name of the author/ inventor) from the non-personal data (artwork/song/painting/invention) may result in copyright infringements.

## Data sources and AI methods
Where does your data come from? Do you collect it yourself or do you use data collected by someone else?

In this initiative, we first need large datasets containing both personal and non-personal data, in order to train the system distinguish between the two.
The safest way to do so would be to use synthetic data, since, as mentioned, personal data imposes additional requirements (and collecting the consent of so many individuals would not be realistic).
Solution: deploy Generative Adversarial Networks (GANs) in order to generate synthetic datasets that preserve the same (or almost the same) properties as the initial data is is based on. For example, GANs will generate large numbers of email addresses, that will train the system to distinguish which email address is personal data (e.g. john.doe@abcompany.com) and which email address is not personal data (e.g. office@abcompany.com). Also, GANs will generate images of people (non-existent people in this case) and images of animals, objects etc., which will train the system to distinguish between the two categories and to label them accordingly when fed with images of real people (personal data) and images of other objects, animals (non-personal data). 

Method to be used: the nearest neighbour method for classification tasks - labelling each data as personal or non-personal and
1) attributing it to the respective dataset (personal/non-personal), if the two categories can be separated OR
2) anonymizing the data that had been labeled as "personal data". The anonymization can be done through various methods, one of them being through GANs again (e.g. AnomiGAN)


## Challenges

What does your project _not_ solve? Which limitations and ethical considerations should be taken into account when deploying a solution like this?

Distinguishing between personal and non-personal data with a high level of accuracy is not an easy task, given the broad scope of what can be considered personal data. It is not limited to a person's name, address, telephone number, but any information that allows the identification of the person. Foe example, the IP address (even a dynamic one) can be considered personal data. Moreover, even when data is not personal data taken individually, when multiple data are processed cumulatively, the outcome can lead to the re-identification of a person. The challenge of this system is therefore to assess the personal character of data on a case-by-case basis taking into account the entire context.

## What next?

How could your project grow and become something even more? What kind of skills, what kind of assistance would you  need to move on? 
First of all, the project would require some already trained GANs, that are able to produce synthetic datasets and to anonymize a given dataset.
Secondly, we would need to train the classification model using the produced synthetic data.

## Acknowledgments

* European Commission Provides Guidance on Mixed Data Sets Containing Personal and Non-Personal Data, Odia Kagan, 2019, https://dataprivacy.foxrothschild.com/2019/05/articles/european-union/european-commission-provides-guidance-on-mixed-data-sets-containing-personal-and-non-personal-data/
* Commission publishes guidance on free flow of non-personal data – Questions and Answers, https://ec.europa.eu/commission/presscorner/detail/en/MEMO_19_2750
