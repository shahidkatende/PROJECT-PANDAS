# PROJECT-PANDAS
# this project shows how pandas library of python is used to analyze data 
import pandas as pd
import numpy as np 
%matplotlib inline  #%matplotlib inline is a functionality that makes sure the plots are inline.  
df_csv = pd.read_csv(r'C:\Users\User\Desktop\test.csv') #method of reading a csv file in pandas to create a data frame ,you copy file path and put r before it 
df_csv #this loads the data frame.
 df_csv['Name']  #choosing the name column from the df_csv dataframe. this method cannot work on row selection
df_csv.loc[0,:] #this is the method of choosing rows in this case we choose row at index position at zero and all columns from start to finish
​df_csv.loc[0:3,'Name']  #allows you to use lables in colum selection 
df_csv.Name #method of choosing name colum from dataframe.if the name column has a dash in it and the name is same as function of data frame it will not work.
​df_csv.loc[df_csv['Age'] >40] #getting results where age is greater than 40 
df_csv.loc[(df_csv['Age'] >40) &(df_csv['Sex']=='male')] #returning results that both conditions 
type(df_csv.loc[(df_csv['Age'] >40) &(df_csv['Sex']=='male')])#helps us to find out out the type of datastructure 
df_csv.loc[(df_csv['Age'] >40) &(df_csv['Sex']=='male')][['Name','Embarked']]#when you want both name and where they embarked. 
df_csv.drop('Parch',axis=1,inplace=True) #dropping column 'Parch',when dropping a column in a dataframe axis=1 
df_csv[ 'PassengerId'].isna()  #isna() returns false if there is no missing value under 'PassengerId' column and true if there is a missing value in the column 

df_csv[df_csv[ 'PassengerId'].isna()] #passing the above boolean experession in the dataframe df_csv to see the rows with missing values in 'PassengerId' column 
df_csv['Age'].mean()#finds mean of 'Age' values 
df_csv['Age'].fillna(df_csv['Age'].mean()) #filling the missing values in 'Age'column with mean of 'Age' values 
df_csv.dropna(subset=['Fare'],inplace=True)#here we are dropping the row where 'Fare' has a missing value. 
df_csv.drop('Cabin',axis=1,inplace=True)#dropping the 'Cabin'column since it has many missing values 
df_csv = pd.read_csv(r'C:\Users\User\Desktop\test.csv') #method of reading a csv file in pandas to create a data frame ,you copy file path and put r before it
df_csv #loads data frame
df_csv['Age'].hist(bins=30) #creation of histogram for 'Age' from df_csv dataframe,bins improves visibility of the histogram.
df_csv['Age'].plot(kind ='hist') # second way of creation of histogram for 'Age' from df_csv dataframe
df_csv['Age'].plot.area(figsize =(15,5))  #figsize increases plot area. 

df_csv[['Age','Fare']].plot.area(alpha=0.5, figsize =(15,5)) # alpha decreases tone color of plot area. 

df_csv.plot.line(x='PassengerId',y='Age',figsize =(15,5))#drawing of plot lines.,figsize =(15,5) increases plot line 


df_csv.plot.scatter(x='PassengerId',y='Age',s=df_csv['Pclass']*50,c='Pclass',cmap='coolwarm',figsize =(15,5))#creation of scatter plot,c='Pclass' represent red color,cmap='coolwarm' reptresent blue colour ,s=df_csv['Pclass']*50 increases colorsize of red color 
df_t.plot.bar(stacked =True,figsize =(15,5)) #creation of a bar plot graph,stacked =True here bars representing different values will be put on top of each other

df_t.plot.box() #creation of box plots 

df_t.plot.hexbin('A','B',gridsize=10)#creation of hex plots,gridsize increase size of hexplots 

df_t.plot.kde()#creation of kernel density entity(kde) plots 

df_t.plot.density()#creation of density plots 
