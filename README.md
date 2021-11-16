<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

# Mixed Datasets

Final project for the Building AI course

## Summary
Mixed datasets contain both personal and non-personal data. My idea is to build an AI algorithm that is able to accurately label personal and non-personal data and sort them in two different categories. This would allow to identify the applicable legal regime to each dataset (containing personal data vs. non-personal data)


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

I believe this is an important topic because we are livind in a data-driven world and we should take advantage and leverage all the potential of the non-personal data uses, especially towards innovation. By being obliged to apply personal data requirements to a dataset that contains both personal and non-personal data (regardless of the quantity of data in each category), the innovation process is slowed down.

## How is it used?

Describe the process of using the solution. In what kind situations is the solution needed (environment, time, etc.)? Who are the users, what kinds of needs should be taken into account?

Images will make your README look nice!
Once you upload an image to your repository, you can link link to it like this (replace the URL with file path, if you've uploaded an image to Github.)
![Cat](https://upload.wikimedia.org/wikipedia/commons/5/5e/Sleeping_cat_on_her_back.jpg)

If you need to resize images, you have to use an HTML tag, like this:
<img src="https://upload.wikimedia.org/wikipedia/commons/5/5e/Sleeping_cat_on_her_back.jpg" width="300">

This is how you create code examples:
```
def main():
   countries = ['Denmark', 'Finland', 'Iceland', 'Norway', 'Sweden']
   pop = [5615000, 5439000, 324000, 5080000, 9609000]   # not actually needed in this exercise...
   fishers = [1891, 2652, 3800, 11611, 1757]

   totPop = sum(pop)
   totFish = sum(fishers)

   # write your solution here

   for i in range(len(countries)):
      print("%s %.2f%%" % (countries[i], 100.0))    # current just prints 100%

main()
```


## Data sources and AI methods
Where does your data come from? Do you collect it yourself or do you use data collected by someone else?
If you need to use links, here's an example:
[Twitter API](https://developer.twitter.com/en/docs)

| Syntax      | Description |
| ----------- | ----------- |
| Header      | Title       |
| Paragraph   | Text        |

## Challenges

What does your project _not_ solve? Which limitations and ethical considerations should be taken into account when deploying a solution like this?

## What next?

How could your project grow and become something even more? What kind of skills, what kind of assistance would you  need to move on? 


## Acknowledgments

* European Commission Provides Guidance on Mixed Data Sets Containing Personal and Non-Personal Data, Odia Kagan, 2019, https://dataprivacy.foxrothschild.com/2019/05/articles/european-union/european-commission-provides-guidance-on-mixed-data-sets-containing-personal-and-non-personal-data/
* Commission publishes guidance on free flow of non-personal data – Questions and Answers, https://ec.europa.eu/commission/presscorner/detail/en/MEMO_19_2750
