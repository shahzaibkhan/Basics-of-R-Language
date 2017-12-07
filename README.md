# R 

#Just to play...
1+2 

#Note: 
# Comments can be made by typing hash sign or you can use control + shift + c
# Control + L = clear terminal screen

# Variable Assignment: 
# We assign values to variables with the assignment operator "=". 
# Just typing the variable by itself at the prompt will print out the value. 
# We should note that another form of assignment operator "<-" is also in use.

x= 1
x+2

#Functions:
#R functions are invoked by its name, then followed by the parenthesis, and zero or more arguments.
c(1, 2, 3) #c converts numeric value into vector 

#Getting Help
help(c) #you can use help() to get the help related to any function 

#With c function, you can even pass strings for vector 
names = c("Owen", "Luke", "Anakin", "Leia", "Jacen", "Jaina")
names

#Some more complex examples:
help(rep); #rep = Replicate Elements of Vectors and Lists
heartDeck = c(rep(1, 13), rep(0, 39))
heartDeck

help(seq); #seq = Generate regular sequences 
y = seq(7, 41, 1.5) #7= starting, 41 is till which it will continue and gap will be of 1.5
y

#to test and play with R we are going to use data set IRIS
data(iris) #to use data set iris 
names(iris) #to get the names 
dim(iris) #to get the dimensions 
str(iris) #to display the structure of iris
View(iris) #this will give you a tabular view 


# ------------------------------------ DESCRIPTIVE STATISTICS --------------------------------------------- #

#Reading from a CSV and then displaying it using view 
dataCSV = read.csv("http://www.calvin.edu/~scofield/data/comma/arsenicInWater.csv")
dataCSV
View(dataCSV)

#Reading counties list from a CSV and then dispaying it 
counties=read.csv("http://www.calvin.edu/~stob/data/counties.csv")
names(counties) #returns the column name 
View(counties)

#MEAN
#to get the entire column data to a varible use $ sign then after it its name 
x = counties$LandArea
mean(x,na.rm = T) #NA = not available values will be removed before computation 

#MEDIAN
median(x, na.rm = T)

#SUMMARY will return us: MEAN MEDIAN MODE MIN AND MAX 
summary(x)

# ------------------------------------ CHARTS IN R --------------------------------------------- #

#1. BAR CHART 
pol = read.csv("http://www.calvin.edu/~stob/data/csbv.csv")
View(pol)
barplot(table(pol$Political04), main="Political Leanings, Calvin Freshman 2004")

View(iris)
barplot(table(iris$Species),main="Species List")

#2. HISTOGRAM 
hist(iris$Petal.Length)

#3. PIECHART
slices <- c(10, 12,4, 16, 8)
lbls <- c("US", "UK", "Australia", "Germany", "France")
pie(slices, labels = lbls, main="Pie Chart of Countries")

# ------------------------------------ INDEPENDENT T-TEST --------------------------------------------- #

#About: The independent t test is used to test if there is any statistically significant difference between two means. 

#4.	Is there a significant "gender" differences for the "overall satisfaction of the job?"
# Write the hypotheses and then test them with an appropriate test. Provide all the necessary values.

# N= There is no difference between gender and overall satisfaction 
# A= There is difference between gender and overall satisfaction 

# P <= 0.05 we reject null and we go for A
# P > 0.05 we accept NULL and that there is no difference 

#t.test Performs one and two sample t-tests on vectors of data.

emp = read.csv('C:/rdata/emp.csv');
t.test(emp$Gender,emp$Satisfaction,paired=TRUE,alternative = "less",na.action=T);



# ------------------------------------ ANNOVA-TEST --------------------------------------------- #


# ------------------------------------ Correlation: Pearson Test --------------------------------------- #


# ------------------------------------ Linear Regression Test --------------------------------------- #
