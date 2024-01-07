# Customer Personality Analysis(ML usning Clustering)
=======================================================================================

### Project Overview & Brief Introduction:
------------------------------------------
Based on the spending habits of the customer, we will segregate the customer into two or three or four any number of clusters 
that is formed based on the algorithm. So, we will segregate the customers.
We will target those customers who like to spend more on things which are newly sold in the market. 
So the companies or firms can target these type of customers so that their products are sold. 
Based on various Features :- 
	Attributes
	----------
		People :-
		---------
			ID: Customer's unique identifier
			Year_Birth: Customer's birth year
			Education: Customer's education level
			Marital_Status: Customer's marital status
			Income: Customer's yearly household income
			Kidhome: Number of children in customer's household
			Teenhome: Number of teenagers in customer's household
			Dt_Customer: Date of customer's enrollment with the company
			Recency: Number of days since customer's last purchase
			Complain: 1 if the customer complained in the last 2 years, 0 otherwise
		Products :-
		-----------
			MntWines: Amount spent on wine in last 2 years
			MntFruits: Amount spent on fruits in last 2 years
			MntMeatProducts: Amount spent on meat in last 2 years
			MntFishProducts: Amount spent on fish in last 2 years
			MntSweetProducts: Amount spent on sweets in last 2 years
			MntGoldProds: Amount spent on gold in last 2 years
		Promotion :-
		------------
			NumDealsPurchases: Number of purchases made with a discount
			AcceptedCmp1: 1 if customer accepted the offer in the 1st campaign, 0 otherwise
			AcceptedCmp2: 1 if customer accepted the offer in the 2nd campaign, 0 otherwise
			AcceptedCmp3: 1 if customer accepted the offer in the 3rd campaign, 0 otherwise
			AcceptedCmp4: 1 if customer accepted the offer in the 4th campaign, 0 otherwise
			AcceptedCmp5: 1 if customer accepted the offer in the 5th campaign, 0 otherwise
			Response: 1 if customer accepted the offer in the last campaign, 0 otherwise
		Place :-
		--------
			NumWebPurchases: Number of purchases made through the company’s website
			NumCatalogPurchases: Number of purchases made using a catalogue
			NumStorePurchases: Number of purchases made directly in stores
			NumWebVisitsMonth: Number of visits to company’s website in the last month
		Target :-
		----------
			Need to perform clustering to summarize customer segments.
problem statement:
------------------
Customer personality analysis is a detailed analysis of companies' ideal customers.
if the company launches any new product, it needs to target a particular set of customers. 

My Project, It helps a business to better understand its customers and make it easier for them to 
modify products according to the specific needs, behaviors and concerns of different types of customers.

### Tools & Technologies:
---------------------------
Programming Language   : Python
Libraries              : NumPy, Pandas, Matplotlib, Seaborn, Scikit-learn
Data Processing        : Feature engineering, handling missing values, and creating new features based on existing data.
Data Visualization     : Seaborn and Matplotlib for creating visualizations to better understand the data.
Machine Learning  Algo : K-means and Hierarical clustering algorithm for customer segmentation.

### the analysis and insights i got through this project are:
------------------------------------------------------------
	(Univariate Analysis)
	- the income column have 24 null values, if i plot hte data, if i plot the distribution of income column if formed left skewed, 
	  So i filled those null values with median values  
	- Based on this Dataset have 5 education Types ('Graduation', 'PhD', 'Master', 'Basic', '2n Cycle')
          i divided into 2 levels under-graduate for who are studied(Basic studies) and Post-graduate for who are studied(Graduation,PhD,Master and 2n Cycle),
	  i observed that most of the data points here are post-Graduated
	- In Material Status i have 8 types :- 'Single', 'Together', 'Married', 'Divorced', 'Widow', 'Alone','Absurd', 'YOLO'
	  i divided into 2 types single for ('Divorced', 'Widow', 'Alone', 'YOLO', 'Absurd') and relationship for('Married', 'Together')
	  64.46% of Customers in the dataset are in "Relationship". 35.53% of Customers in the dataset are "Single".
	- i Combining TeenHome and KidHome into a single column as Kids column to reduce the number of dimension
	  50.35% of Customers in the dataset have 1 kid. 28.48% of Customers in the dataset have no kids. 18.79% of Customers in the dataset have 2 kids. 2.36% of Customers in the dataset have 3 kids.
	- here i have products are Sweets, Fruits, Meat, Gold, Fish and Wine, and a person is spent amount for each product on different kind 
	  So i Combined all product columns into a single column as Expenses to reduce the number of dimension
	- A customer urchase things in different wayes are like through company websites or companies catalogue or Directly with help of Stores
	  So i Combined all product columns into a single column as NumTotalPurchases to reduce the number of dimension   
	- i converted the Year_Birth into Customer_Age with help of Python TimeStamp()
	  Most of the cutomers we have are in middle age i.e between 35-70
	- i have a Date Column that customer's enrollment with the company, from this coumn i extracted the dayes it means 
	  it will tell us The number of days a customer is registered in the firm's/ Store's database, with help of latest recorded date or maximum date
	  Most of the customers are regular to the shopping for 200-850 days

	(Bivariate Analysis)
	- the Post graduated people spends more than the UG people
	- single and married people have the same spendings
	- parents with 1 kid spends more than the parents who are having 2 or 3 kids
	- And who are doing more purchases they have more expenses
	- People who are in middle age they have less expenses(30 to 60) than others
	
	- i did a data preprocessing(LabelEncoding) for Education and Material_Status categorical features 
	  except this columns i performed for scaling technique for all the numerical features, this all are different Units.

### while doing this project i faced some Challenges:
----------------------------------------------------
	- Data Cleaning Challenges: Dealing with missing values and outliers in the income and age columns. 
	  Overcame by replacing missing values with median, handling outliers, and ensuring data integrity.
	- Feature Engineering Complexity: Creating meaningful features from date columns required careful consideration. 
          Overcame by extracting relevant information and transforming it into usable features.

### models building:
-------------------
	- i tried models for this project as K means and agglomeritive clustering from hierarical clustring 
	- with help of k menas clustering i got 2 is best clusters size from eucledian distance with loss of 1100 and the Silhouette Score is 60%
	- with help of aglomeritive clustering also i got 2 is best clusters size from eucledian distance with loss of and the Silhouette Score is 80%

### Conclusions:
------------------
	Cluster 1:
		- People with less expenses
		- people who are married and parents of more than 3 kids
		- people which low income
	Cluster 2:
		- people with more expenses
		- people who are single or parents who have less than 3 kids
		- people with high income
		- Age is not the criteria but it is observed to some extent that people who are older fall in this group
