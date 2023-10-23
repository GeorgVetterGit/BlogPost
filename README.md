# Purchase Pattern Analysis

## Overview
The analysis of purchasing patterns is based on purchasing receipts from Picnic in PDF format. These purchasing receipts are put into a structured form and then three questions are answered:
1. What are the 10 most common items we buy regularly?
2. What items do we often buy together?
3. What influence does the price reduction and the season have on our shopping behavior?

## Table of Content
1. [Installation](#install)
2. [Motivation](#motivation)
3. [Content](#content)
4. [Results](#results)
5. [Usage](#usage)
6. [Author](#author)

## 1. Installation {#install}

### 1.1 Python

This algorithm was created in python v 3.11.

The following packages are used and must be installed beforehand:
#### pandas
```
pip install pandas==2.0.3
```
#### numpy
```
pip install numpy==1.23.5
```
#### tika
```
pip install tika==2.6.0
```
#### sklearn
```
pip install scikit-learn==1.3.0
```
#### glob
```
pip install glob2
```
#### seaborn
```
pip install seaborn==0.12.2
```
#### matplotlib
```
pip install matplotlib==3.7.1
```

### 1.2 Excel
The input and output of the algorithm is in .xlsx format, so an up-to-date Excel version might be necessary.

## 2. Motivation {#motivation}

Do you believe in the power of data to uncover the secrets of shopping? Join me in this adventure as we analyze the contents of your cart and decode the patterns and preferences that shape our shopping decisions.

We've been shopping for our everyday goods online for several years. Since these are everyday items that we need again and again, we avoid the real shopping experience here and thus save a lot of time. Over the past few years, we have accumulated so many shopping records that it is worthwhile to use data science methods to mine this treasure of data and take a closer look at our shopping behavior.

## 3. Content {#content}

The following section contains a description of the files in this package.

### 3.1 pdf_to_table.ipynb
The file extracts data from the PDF purchasing documents and structures it into a dataframe, which is saved as an Excel file. The individual technical details are described in the notebook.

### 3.2 analysis.ipynb
The file contains all the steps for analyzing the database, which was created in pdf_to_table.ipynb. In particular, the questions asked are answered here. The details of the analysis can also be read in the notebook.

## 4. Results {#results}

### 4.1 What are the 10 most common items we buy regularly?
Identifying the most common 10 items was done quickly. We bought mostly dairy products and cheese, but also fruits and vegetables. Also bread. So you can see that we hardly eat meat, but we don't eat a vegan diet. Also, you can see that we have a dog, as treats for the dog is the fifth most common item.

### 4.2 What items do we often buy together?
It can be seen that pine nuts and tortelloni with cheese are always bought together. Often also in combination with tortelloni with spinach. From this you can see one of our favorite dishes: Tortelloni with pine nuts, cream cheese and zucchini. The latter two items just don't show up in the matrix because I had previously removed them (see above). I also see a high correlation between Parmesan and chopped tomatoes, as we like to use both items in combination for a lasagna.

If you would look at the other correlations in combination with our cookbook, more logical correlations would emerge, although I suspect a coincidental correlation in some of the correlations.

### 4.3 What influence does the price reduction and the season have on our shopping behavior?
I used linear regression analysis to explore the influence of price reductions and seasons on shopping behavior. Therefore, I used the amount of products purchased at a grocery store as the dependent variable and considered dummy variables for different seasons and price reduction indicators. The results revealed that one group of products was entirely independent of price and season, with an R² of 1 and all influencing factors at 0. Only one product, red wine, achieved a relatively high R² (>0.8), primarily purchased in winter. For other products, the R² was below 0.3, making it challenging to determine the extent of influence from these factors. The coefficients for the influencing factors are provided for the product with a high R².

## 5. Usage {#usage}

To use the algorithm, only the respective input file must be adapted. Then simply run the notebook or the script and find the corresponding output file in the same folder.

## 6. Author {#author}
Georg Vetter
#### 6.1 Contact
georg.vetter@westnetz.de