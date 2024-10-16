This project contains scripts and outputs of three different machine learning algorithms used to classify which patients would be more or less likely to be readmitted to an emergency room within 30 days. ML algorithms used were a standard battery of bagging, random forest, and XGBoost. XGBoost resulted in the best results with the highest accuracy and precision scores.

I would say the bulk of the work went into the XGBoost version, so if you want a quick glance at what my process was, take a look there. 

Lessons learned: 

This was my first real dive into ML. The goal of this project was to use MIMIC data to create a model that could classify whether patients, given XYZ features (whether it be physiological data like heart rate, blood pressure etc. or demographical data like age, sex, insurance status etc.), would be re-admitted to the hospital within 30 days of first admittance. Basically, the gist of the question was, if a patient presented to the ER with some combination of these various features, would they be re-admitted to the hospital again within 30 days. The utility of a tool such as this would be to better control ER flow of patients and give hospitals indications on whether a certain patient may be a candidate for re-admittance to the hospital.

The three main lessons that I learned here was that, one, I should have come at this project with a probabilistic mindset instead of a classifying mindset, with the question: "What are the chances that someone with XYZ features (physiological, demographic etc.) becomes a re-admit to this ER?".

Two, working with large dataset can be a challenge and frontloading the work of selection the proper dataset and feature selection can really help save time in the backend. This also really can be helpful in scoping a project and not letting it blow up to a massive scale quickly with lots of targets to hit.

_Caveat here: Given more time, I would definitely have conducted my dataset curation in SQL with much, much more detail. Again, I was limited by both space (literal disk space) and time to get this project running and written up but that's always the case for any project, isn't it?_

Three, the context of the data really matters. The model is only as good as the data I bring to it. Especially in healthcare setting where location of hospital, frequent users' demographics, and various other socio-economic level factors can impact the context of the data (not just the quality of the data). So, when answering the question of what features best explains when someone is re-admitted to the hospital, we have to be wary not to over generalize apply our answers to other contexts. That'll require it's own separate processing.
