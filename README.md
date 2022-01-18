# phase-4-project

## Outline of this repo
Contained in this repo I have 4 files I have
1. phase4_final - this is the jupyter notebook with the whole analysis of the problem I was adressing 
2. Mod4_finalproject_PPP1 - this is a non-technical presentation of the problem I was adressing
3. zillow_data.csv - this is the data I used for this project 
4. photos - this is a folder containing all the images that i have used in this Readme

## The outline of this project

#### I am a consultant for a fictional real-estate investment firm. The firm has asked me to find out what are the top 5 zip codes for me to invest in.

### How does this help

Realestate has conventionally been quite a traditional market. Experience and qualitative knowledge has been a large driver in investment decisions in the indisutry. 

However, episodes like the financial crisis of 2007/08 along with many other episodes have shown that it isnt enough to assume that realestate will always go up. 

In addition to this the realestate market is getting ever more competitive. With inflation rising and the value of money going down investors are looking for alternative assets to store money in. Realestate is at the forefront of this race. Thus, inorder to make make the best decisions in a competitive space great analysis must be done before investment decision are done.

Being able to leverage the plethora of data on the realestate market is vital. Even if the conventional wisdom of 'realestate is always goign to go up' is assumed PE funds typically target a 25%IRR and a 2.5X mom over a 5-10 year time frame. This is hard to achieve thus leveraging data to make sound decisions is important.


### My role in this

Given the necessity to use data to make investment decisions i have the role to analyse the data available to suggest regions which would be good for investment. My goal is to narrow down the search to a 5 zipcodes which an investment firm could spend time and energy looking into before deciding exactly where and what to invest in.

## Filtering the data

![data](https://github.com/SaifuddinAnjarwalla/phase-4-project/blob/7e04a7c75e005f5285a5ce2df1402ad47cdd6583/photos/data.jpg)


I decide to filter the data based on zip code. 

I take the top 20% of zip codes as this would give me property that is more urbanized. This is preferable to me as an investor. 

From the top 20% I decide to filter it down even more. 

I choose data that is in the 60th quantile of CV to reduce risk.

I decide to choose properties that are 10% above the average value (of the last 12 months value) and 15% below the average value (of the last 12 months value). 

I calculated the ROI for all the remaining properties and chose the properties with the highest ROI.


## EDA

![housep](https://github.com/SaifuddinAnjarwalla/phase-4-project/blob/7e04a7c75e005f5285a5ce2df1402ad47cdd6583/photos/housep.png)


![housed](https://github.com/SaifuddinAnjarwalla/phase-4-project/blob/7e04a7c75e005f5285a5ce2df1402ad47cdd6583/photos/housed.png)



## Building the model 

I go through each region individually and build each an arima model. I check for stationarity adn look at the ACF and PACF plots to generate teh PQD values for the arima model. 

## Forecasts and recommendations

I then forecast the models for 1,5 and 10 years into the future. I decide to use 5 years as the invesmtne horizon adn filter the 7 datapoints i have to 5 based on the 5 year ROI. These are thus my recommendations.

![forecasts](https://github.com/SaifuddinAnjarwalla/phase-4-project/blob/7e04a7c75e005f5285a5ce2df1402ad47cdd6583/photos/preds.png)

The Regions i would invest in, in order of preference are. 
1. 70809
2. 3820
3. 3038
4. 29461
5. 70808

This is because the ROI's for these 5 properties were highest after 5 years.

## Conclusion

1. We started of by explaing the project and 
2. We first analyzed the data. 
2. By filtering the data with specific criterias we came up with a subset of regions to analyze. 
3. We created a time series model on these regions and forecasted them into the future. 
4. We then calculated the ROI in the future and narrowed down the top 5. 

In the future if i had more time i would like to optimise on the following things:
1. Run a model that creates a time series model for every region.
2. Optimise on when to sell - perhaps there is a better timeframe as opposed to a fixed 5 year horizon (maybe it is predicted that some properties will peak after 6.7 years for example)
3. Optimise on features other than ROI
4. Loop more deeply at different property types (data provided)

