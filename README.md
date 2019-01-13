# Predicting Maternal Mortality Rate of the World
------------------------------------------------------

### We Wanted to create a machine that will be able to predict a women's chance of dying given the country she is in, the country's GDP, it's expenditure on healthcare, the fertility rate of women of that country, as well as if women are provided for additional benefits such as paid maternal health care.

___________________________________________________________________________

#### Gathering the Data:

Our data came from worldbank data. We collected several csv files, compiled them into one for our baseline. Our target was predicting mortality rate with the rest being our independent variables.

[World GDP](https://data.worldbank.org/indicator/NY.GDP.MKTP.CD) ; 

[Fertility Rate](https://ourworldindata.org/fertility-rate) ; 

[Population](https://data.worldbank.org/indicator/SP.POP.TOTL) ; 

[Maternity Leaves](http://databank.worldbank.org/data/embed/paid-unpaid-maternity-leaves/id/b4306aae) ;

[Maternal Mortality Rate](http://databank.worldbank.org/data/embed/maternal-death-rate/id/946477a1) 
________________________________________________________________________________

## EDA of our Data

After making a full CSV and converting it to a dataframe, we did some basic Explotarory Data Analysis. First we removed all null values, and cleaned up our data for any missing values. We also scaled and adjust to create a better fit model.

This is what our dataframe consisted of:

<img width="908" alt="screen shot 2019-01-12 at 9 00 24 pm" src="https://user-images.githubusercontent.com/41834786/51080667-0b3a4700-16ae-11e9-9f3e-f3bc9a9c00f1.png">


Here is also a correlational matrix: 

<img width="476" alt="screen shot 2019-01-12 at 9 03 42 pm" src="https://user-images.githubusercontent.com/41834786/51080712-de3a6400-16ae-11e9-838e-aec0cfff4194.png">
_________

## Modeling

For our first test, we chose to see the affect of fertility rate on mortality rate. We hyposthesized that there would be a strong positive correlation. This test proved that to be true:

<img width="446" alt="screen shot 2019-01-12 at 9 04 06 pm" src="https://user-images.githubusercontent.com/41834786/51080754-4be69000-16af-11e9-964b-1b829eb938d8.png">

Then we wanted to compare a country's GDP in relation to it's expendeture on healthcare and it's effect on maternal mortality rate. We found an inverse relationship (negative correlation) this time. This makes sense as we are supposed to observe lower maternal mortality rate on countries who can provide healthcare for the women.

<img width="869" alt="screen shot 2019-01-12 at 9 05 00 pm" src="https://user-images.githubusercontent.com/41834786/51080793-d4fdc700-16af-11e9-859c-668834b20776.png">

Finaly, we made a model with some saling and feature tweak: We found that our model can predict if a woman is to survive childbirth in a given country with a confidence of adjusted 75%. 


<img width="715" alt="screen shot 2019-01-12 at 9 21 18 pm" src="https://user-images.githubusercontent.com/41834786/51080807-23ab6100-16b0-11e9-8d20-2481411f32a9.png">

Of course there are few issues here, even after scaling. Our p-values are relatively high for some features. This is due to some features having less samples than the rest. In the future, we would like to run PCA and additional GridSearch based model to find a criteria selection that would improve this model even more.

Here is our last picture graphing our model's ability to predict mortality rate:

<img width="542" alt="screen shot 2019-01-12 at 9 05 48 pm" src="https://user-images.githubusercontent.com/41834786/51080824-813fad80-16b0-11e9-9b0b-cc04df65727a.png">

There are some outliers, but these are the extreme cases not the norm. As you can see, even with those issues our model came very close to predicting with high accuracy a woman's chance of survival given the country's gdp, healthcare expendature and fertility rate.

Thank you for reading.
