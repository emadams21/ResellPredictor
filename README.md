![Jordan 1 Cover for Readme](https://user-images.githubusercontent.com/115181745/229978370-64caf802-dae5-4698-99f8-049ba463d4e5.png)
# Resell Predictor Tool

Are you a sneakerhead that has trouble finding the next hottest shoe to collect or Resell? Well, I've created a model based on 90,000 different shoe sales from StockX one of the most popular reselling websites in the world. Our model is so well that we can predict within $70 of the actual shoe price. (See below for further details.)    
# Business Understanding

The business problem that I am trying to solve is to help high-end shoe resellers be able to gain competitive advantages when it comes to knowing what shoes to buy, giving them the most bang for their buck. I want them to be able to put in what type of shoe they want and then predict the reselling price to potentially predict profit.

# Data Understanding

The data in this project consist of a random sample of all U.S. Off-White x Nike and Yeezy 350 sales from between 9/1/2017 and 2/13/2019. 
This was from a data contest that StockX provided. To create this sample, StockX collected a random, fixed percentage of StockX sales for each colorway, on each day, since September, 2017. So, for each day the Off-White Jordan 1 was on the market, StockX randomly selected sales from each day. The sample was limited to U.S. sales only.

# Data Discoveries
After cleaning the data and renaming columns to best suit this project I did an initial analysis to test the spread of different resell prices to determine if they were in a certain range or are their shoes on a spectrum. As shown below what I discovered is that this data set contains shoes on various ranges form high-end collectible shoes to middle to lower-end shoes. 

![Resell Price Image](https://user-images.githubusercontent.com/115181745/229978655-c7788942-df74-4e85-905d-4aa869968456.png)

I took into account Shoe Size, Colors, Retail Price, and shoe brand for the physical parts of the shoe. For colors, I had to incorporate a separate data set and one hot encode that data set to make it easy to identify which color is which.  From a non-physical standpoint, I restructured the way time was represented to make it easier to put into the model. I decided to reorganize the Release Dates and Order dates into seasons and years so I could just one-hot encode them together into the model. Now that I had all my features listed out I needed to see which features correlated with each other so I could choose the best model to go with.  I ended up creating a correlation matrix as shown below to map out which features show some correlation to each other.

![Correlation Matrix](https://user-images.githubusercontent.com/115181745/229978586-6afc90c0-779e-43d0-87b3-b2f809b5ef95.png)

This correlation matrix had some really interesting findings. I discovered that there was some positive correlation between the color red on profit, Resell Price, and profit ratio. However, there were some inverse relationships between Resell price and the original retail price or an inverse relationship if the color of the shoes is grey.

# Modeling and Evaluation
The classification that I was aiming for was to be able to predict the Resell price for any given shoe this also indicates that this will be a regression problem because it is calculating the actual $ dollar value of the shoe. 

To help me choose a model that would best suit me I wanted to create a pipeline to help me choose the best model possible. I wanted to choose between a decision tree regression model and Random Forest Pipeline to help me identify the specific shoe and its resell price. I also wanted to test the XGBoost model to show which features are impacting the Resell price the most. Through most of my testing, XGBoost and the Random Forest Pipeline went back and forth on accuracy initially. I chose Random Forrest because It was more accurate most of the time. 

# Conclusion

I initially got an MSE (Mean Squared Error)  of $123.93 from the actual resell price and an improved model accuracy of 89%. I was extremely pleased with these results because they didn't show any signs of over or underfitting.

However, the issue within the shoe reselling industry is that shoe prices are extremely volatile and change every day. This is why I chose to incorporate MAE(Mean Average Error) to mitigate the volatility of how the resell industry works. The average Error ended up being $70.30 which is awesome to help create a more precise range each shoe could resell for.

My next steps are soon to create an interactive app to be able to predict these same 50 different shoes today!

# Repository Navigation
These are guidelines to be able to see the code from a reproduceability standpoint.

1.[Final Notebook](https://github.com/emadams21/ResellPredictor/blob/main/Resell%20Predictor%20Tool%20Master%20Notebook.ipynb)

2.[Stockx Capstone Project Presentation.pptx](https://amedeloitte-my.sharepoint.com/:p:/g/personal/emadams_deloitte_com/EWWhJKfu1DBNsU5aaA0HdGIB1biLY0AW36Qg2yRmN090xw?e=CBT87e)

3.[Reproducability instructions are also found in the Final Notebook Linked Here!](https://github.com/emadams21/ResellPredictor/blob/main/Resell%20Predictor%20Tool%20Master%20Notebook.ipynb)
