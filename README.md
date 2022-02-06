# starbucks_challenge

## Content:

1. [**Installation**](#Installation)
2. [**Motivation**](#Motivation)
3. [**Notebook**](#Notebook)
    * [**I**](#Part-I:-Data-examining): Data examine
    * [**II**](#Part-II:-Data-cleaning): Data cleaning
    * [**III**](#Part-III:-Data-exploring): Data exploring
    * [**IV**](#Part-IV:-Conclusion): Conclusion
4. [**Operation**](#Operation)
5. [**License**](#License)

----------------------------------------------------------------------------------------------------------------------------
## Installation:

* **Python** - There should be no necessary libraries to run the code here beyond the **Anaconda distribution of Python**. 
* **Pandas** - Data analysis and manipulation tool.
* **Numpy** - Numerical computing tools.
* **Matplotlib** - Creating comprehensive visualizations tool.

------------------------------------------------------------------------------------------------------------------------------
## Motivation:

In order to understand and find out the **preference of offers for existed customer**, analysing purchased dataset which provided by **Starbucks**. Also, seeking other insights from it, such as customer feature, financial condition, etc. 

-------------------------------------------------------------------------------------------------------------------------------
## [Notebook](https://nbviewer.org/github/yayuchen/starbucks_challenge/blob/main/Starbucks%20.ipynb#2):


### Part I: Data examining

1. **Portfolio**: details of offers, including types, ids, rewards, difficulties and durations.
 
2. **Profile**: details of customers, including genders, ages, ids and incomes.
 
3. **Transcript**: details of records, including customer ids, events and values. In event feature, there are 4 different values which are offer received, offer viewed, offer completed and transaction. If event is transaction, the correspond value feature would show amount and numerical value in dictionary format, otherwise, it would display offer id.

---------------------------------------------------------------------------------------------------------------------------------

### Part II: Data cleaning

1. Merging **3** different dataset into 1 by key columns, such as offer ids and customer ids.

* Merge transcript with portfolio with offer ids
![merge 1](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/merge%201.png)

* Merge above with customer ids and transfer NaN value in income column to 0
![merge 2](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/merge%202.png)

* Reorder columns
![merge 3](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/merge%203.png)

2. Extracting data which **excludes** transaction event.

3. Converting numerical feature values into bins, filling none value with np.nan(NaN) and transfering offer ids into int values(1 ~ 10).
4. Transfering offer ids into int values(1 ~ 10).
5. Dividing data into subsets by different events.
6. Group dataset by customers ids, customer feature and offer ids, and reform a new dataset.
![offer merge](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/offer%20merge.png)

7. Merging group subsets into a new dataset with differnt event of offer ids.
![merge event](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/event%20merge.png)

8. Calculating viewed and completed rate for each customer.

* Count frequency of each event and calculate rate
![cal rate](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/cal%20rate.png)

* Convert numerical value into bins
![convert num](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/convert%20num.png)
![result](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/convert%20range.png)

9. Extracting id numbers as new column features.

* Extract offer ids from different events
![offer list 1](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/offer%20list%201.png)

* Extract double or multiple offer ids and intersect ids
![offer list 2](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/offer%20list%202.png)

------------------------------------------------------------------------------------------------------------------------

### Part III: Data exploring

1. Examining overall customer features, such as ages, incomes and genders.

* Gender distribution

![genders](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/gender.png)

* Ages: **1**. below 35 year; **2**. 36 to 50 year; **3**. 51 to 65 year; **4**. 66 to 80 year; **5**. 81 to 95 year; **6**. above 96 year
 
 ![ages](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/ages.png)
 
 * Incomes: **1**. below $20000; **2**. $20001 to $40000; **3**. $40001 to $60000; **4**. $60001 to $80000; **5**. $80001 to $100000; **6**. above $100001
  
  ![incomes](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/incomes.png)
  
 2. Viewing customer features by different viewed and completed rates.
 
 * Genders with different rates
 ![genders with rate](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/vc%20gender.png)
 
 * Ages with different rates
 ![ages with rate](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/vc%20age.png)
 
 * Incomes with different rates
 ![income with rate](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/vc%20income.png)
 
 3. Inspecting offer frequency with different events by different rates.
 
 * Offer frequency
 ![offers view](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/offer%20view.png)
 
 4. Displaying unique or multiple offer counts by different completed rates.

 * Viewed and completed offer frequency 
 ![vc offer](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/vc%20count.png)
 
 * Completed but not viewed offer frequency
 ![vnc offer](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/vnc%20count.png)
 
 5. Revealing the relation between viewed and completed.

 * Completed portion in viewed rate 0 to 0.25
 ![vr1c](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/vr1c.png)
 
 * Viewing genders and incomes for who had completed rate over 0.5
 ![income vr1c](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/income%20vr1c.png)
 
 * Completed portion in viewed rate 0.26 to 0.5
 ![vr2c](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/vr2c.png)
 
 * Viewing genders and incomes for who had completed rate over 0.5
 ![income vr2c](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/income%20vr2c.png)
 
 * Completed portion in viewed rate 0.51 to 0.75
 ![vr3c](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/vr3c.png)
 
 * Viewing genders and incomes for who had completed rate below 0.5
 ![income vr3c](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/income%20vr3c.png)
 
 * Completed portion in viewed rate 0.76 to 1
 ![vr4c](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/vr4c.png)
 
 * Viewing genders and incomes for who had completed rate below 0.5
 ![income vr4c](https://github.com/yayuchen/starbucks_challenge/blob/main/photos/income%20vr4c.png)IV
 
 -----------------------------------------------------------------------------------------------------------------------
 
 ### Part IV: Conclusion
 
 
 #### 1. Customer features between genders, ages and incomes
 
 * **Male** has majority portion in this dataset.
 * **None** gender is more likely a group of retired customers who's age is oldest with lowest income.
 * **Other** gender is the minority group in this dataset which occupied **1.2%** only.
 
 #### 2. Relation between ages and incomes in different viewed and completed rates
 
 * **None** gender customer had significant viewed rate but low completed records, we could assume that due to their **low income profile**, it made them have interests for viewing offers but hesitating to purchase.
 
 * In the inspection by different viewed and completed rate, it appeared that customers who's **age between 51 to 65 has significant viewed and completed records**, and we could guess that the reason for this group tend to purchase due to their **stable financial condition**. However, only **age over 96** group had more records than them when **completed rate was between 0 to 0.25**. 
 
 #### 3. Insights from customer features
 
 * **Male is younger** than female.  
 * **Male had more viewed** records than female.
 * **The average of incomes of female is higher** than male.
 * **Female had purchased more** than male, especially with higher income.
 * **Customers who have higher income were more likely to complete more offers without viewing**.
 
 #### 4. Inspection of offers
 
 In my research, it can be divided into **4** different patterns. 
 
 * **Never completed**: **Informational type** only.
 * **Higher viewed**: offer id 1, 2, 6, 7 and 9 had more viewed than others, **bogo** occupied 60% and **discount** is 40%.
 * **Higher viewed and completed**: offer id 6, 7 and 9 had more viewed and completed records, **dicount** occupied 67% and **bogo** is 33%.
 * **Higher completed without viewed**: offer id 4, 5 and 10 had more completed without viewed records, **dicount** occupied 67% and **bogo** is 33%.

 The difference between reward, difficulty and duration of completed records:

 Average of rewards - **3.3**(higher viewed and completed), **4**(higher completed without viewed)
 Average of difficulty - **7.3**(higher viewed and completed), **11.7**(higher completed without viewed)
 Average of duration - **7.3**(higher viewed and completed), **8**(higher completed without viewed)
 
 #### 5. Preference of customers
 
 * Whether viewed or not, **discount type** seems more attractive than bogo type.
 * For customers who had **viewed and completed** pattern, it seemed like they prefer to accomplish **less difficulty and lower reward** offers.
 * For those who **completed offers without viewed**, because they did not view, so they would not know about any details of offer. Therefore, the only factor for these customers still had chance to accomplish is **longer duration for some difficult offers**. 


>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>


## Operation:
* Git clone repo:

      git clone https://github.com/yayuchen/starbucks_challenge.git

>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>>
## License:
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
