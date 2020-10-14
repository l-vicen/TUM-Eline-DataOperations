# Documentation of task

In addition to the code documentation, I have created this file to summarize the: task objectives, procedures and results.

## Task Objectives

1. __Dummy Variable: NaturalPerson__

        Natural Persons == 1
        Non-natural Persons == 0

2. __Dummy Variable: GenderManual__

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


## Results