# Documentation of task

In addition to the code documentation, I have created this file to summarize the: task objectives, procedures and results.

## Task Objectives

1. __Dummy Variable: NaturalPerson__

        Natural Persons == 1
        Non-natural Persons == 0

2. __Dummy Variable: GenderManual__

        GenderManual(Natural Persons only): 
                        
                        Male (M) == 1;
                        Female (F) == 0;

        GenderManual(Non-natural person):
                
                        Non-natural person  == 'empty' (NaN)         ;

## Challenges

1. __Dummy Variable: NaturalPerson__

        - Real world-data -> incompleteness (columns), diverse and "very big" amount of data;
        - Find pattern in columns that were complete;

2. __Dummy Variable: GenderManual__

        - Real world-data -> incompleteness (columns), diverse and "very big" amount of data;
        - Gender classifier;
        
## Procedures

1. __Dummy Variable: NaturalPerson__

        - Used following columns: dmFullName, dmGender, dmCountry,dmAge & dmBirthDate. (order of the columns regards the "completeness" of each of them.)
        - Come up with 3 filters using dmFullName. Here I have encoded the data using a custom binary technique investigating the strings of the cells based on these search:
                1. Checked if observations had person titles, e.g. Dr., Madam, Prof. ...;
                2. Checked if observations had numeric symbols, e.g. 0, 1, 2 ...;
                3. Checked if observations had entity titles based on the locations with most observations (checked using dmCountry), e.g. Germany was one location so I did a string check on GmbH, AG, e.V. ... ; 
        - Come up with a 3 star scoring mechanism using dmAge, dmGender and dmBirthDate. I gave one star for each column in case the observation had a value in these columns. If observation scored a star rating bigger than 2 (so 2 stars), I wouldn't review the observation manually. 
        
2. __Dummy Variable: GenderManual__

        - Played around with 2 existing ML algorithms to classify/predict Gender based on ones firstname. 
                1. NaiveBayes (Accuracy: 63% test data, 98% train data)
                2. Decision Tree (Accuracy: 86% test data, 98% train data)
        - Steps:
                - From task 1 I knew 119046 observations were Gender reliable because they had inputs under the dmGender column;
                - The rest, 4466 observation, were distributed (result from task 01) in 2195 non-natural (after 2 manual revisions) & 2271 natural;
                - Out of the 2271, after manual revision (because 146 obs. didn't had a firstname) and the Gender classifier I have used, I got that 1448 out of 2271 were males and 823 females; (Decision Tree Method with 86% accuracy.)
                - Encoded and merged all data back together. 

## Results

- Two dummy variables;
- Natural Person defined by procedure description above. __In short:__ 2195 non-natural, 121317 natural;
- Same for Gender Manual. __In short:__ 100025 Males, 21292 Females & 2195 nan;