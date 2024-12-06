# Titanic Tabulation

<br>

The RMS Titanic was a British ocean liner that unfortunately crashed and sunk in the early 1910s. The story of the Titanic's sinking has become a cultural staple in modern-day society, and therefore records of the passengers have been well preserved. In our Full-Stack Development class in the Brooklyn Steam Center, we have conducted various data visualizations using Jupyter Notebooks, Pandas, and Matplotlib. Here I will be sharing the results of my data analysis, asking some intriguing questions regarding the passenger data, and hopefully debunking or confirming my impressions of the Titanic through the analysis of objective data.

## Column Breakdown:

<img src="images\titanic_tabulation\titanic_columns.png" alt="A sample of a few items from the titanic dataset">

<br>

Before analyzing the data, It is important to understand the raw data and what its columns represent. The provided Titanic passenger dataset is sorted by 12 unique columns.
### PassengerID: A unique ID given to each passenger 
### Survived: A true or false value for whether that passenger had survived or not
### Pclass: The ticket class the passenger had ridden in
### Name: The full name and title of the passenger
### Sex: The sex of the passenger
### Age: The passenger's age at the time of boarding
### SibSp: The amount of siblings and/or spouses the passenger had present on the ship
### ParCh: The amount of parents and/or children the passenger had present on the ship
### Ticket: The unique ticket ID of the passenger.
### Fare: The price paid for tickets by the passenger
### Cabin: The cabin number the passenger had stayed in.
### Embarked: The port in which the passenger had embarked on the ship.

<br>

## Question 1: What are the average age groups of the passengers?

<img src="images\titanic_tabulation\q1.png" alt="Graph for question 1">

<br>

To begin, I wanted a general idea of how old the passengers of the Titanic were. Analyzing the age data of the passengers would give me insight into the kind of environment present on the Titanic. Based on the histogram, most passengers were between the ages of 20 and 40, relatively young to middle-aged people. The abundance of younger passengers implies that, despite the kinds of high-ranking passengers, the Titanic was certainly more of a spectacle or leisure trip than a place for the affluent to convene.

<br>

## Question 2: How many passengers rode in each class?

<img src="images\titanic_tabulation\q2.png" alt="Graph for question 2">

<br>

Next, I wanted to see the amount of passengers who rode in each class. My idea of the Titanic was of a luxury ship full of rich aristocrats and businessmen and women, so it was surprising to see that the majority of all passengers rode in third class. This may indicate that many people had used the Titanic as a practical means of transportation rather than just a luxury cruise experience.

<br>

## Question 3: How many passengers rode with family?

<img src="images\titanic_tabulation\q3.png" alt="Graph for question 3">

<br>

The "SipSp" and "Parch" columns piqued my interest, as the idea of recording the presence of family was an interesting and unexpected concept. Likewise, I expected most people to be riding alone or with friends, but the data once again contradicts my preconceived conclusions as the majority of passengers rode with at least one family member.

<br>

## Question 4: Which port of embarkment had the highest survival rate?

 <img src="images\titanic_tabulation\q4.png" alt="Graph for question 4">

 <br>

 Out of all the analysis questions, this was definitely my favorite. I was curious which port statistically had the best odds of survival for the passengers who embarked there, i found the idea that there was a statistically beneficial port to embark from very interesting. Despite my findings, It is important to note that, despite the results shown here, there is not necessarily a correlation between the port of embarkment and survival rate, it could be a coincidence that the "C" port had the most survivals.

<br>

## Question 5: What was the most common passenger class of male passengers without a recorded age?

<img src="images\titanic_tabulation\q5.png" alt="Graph for question 5">

<br>

Finally, a question compounding passenger age (or lack thereof,) sex, and class. The passengers with a lack of age recorded caught my eye, and my initial theory is that these were of high class who, for one reason or another, desired to keep their age anonymous. However, based on the results, I infer that the lack of a recorded age is simply human error, and because there were more third-class passengers overall, there were more third-class passengers without a recorded age.

<br>

## Conclusion

<br>

Ultimately, the analysis of the Titanic passenger dataset provided the context needed to answer some interesting questions I had about the Titanic’s purchase, as well as served as an excellent introduction to the use of Jupyter Notebooks in data science. Data analysis such as this can be employed in a variety of fields, to grant a greater subjective understanding based on objective data and to help guide decision-making in the future based on what was analyzed.
