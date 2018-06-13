# Investment-Potencial-of-NYC-Real-Estate-Market
Course project of DS-GA 1001: Introduction of data science

In our project we have built up a model by supervised learning method to discover relation between 
neighborhood features and high-potential area in New York real estate market. We used Linear SVM as 
baseline model, then improved the performance by testing precision scores of highest investment 
potential class of Decision Tree and SVM with different parameters. The result shows that the East
Queens and North Bronx have high investment potential in records. More detail please refer to [report](https://github.com/Netjimmy/Investment-Potencial-of-NYC-Real-Estate-Market/blob/master/houseeasy-final-report.pdf)

## Data Preparation
The data are from 2 different resouces
#### 1. [StreetEasy](https://streeteasy.com/blog/download-data/)
#### 2. [NYU Furman Center](http://app.coredata.nyc/)

Our primary resource of house price and inventory is StreetEasy, and NYU Furman Center provided neighborhood-level information on housing markets, home affordability, land use, demographics, and neighborhood conditionsand. However, the former has 130 neighbors, but the later only has 55. The challenge was to align the difference of number of neighbors

### Feature Definition
<img width="747" alt="screen shot 2018-03-21 at 11 43 33 pm" src="https://user-images.githubusercontent.com/15644582/37750413-40149f50-2d63-11e8-9f1a-5448b29ea297.png">

### Target Definition
<img width="231" alt="screen shot 2018-03-21 at 11 43 48 pm" src="https://user-images.githubusercontent.com/15644582/37750441-6b7ed85e-2d63-11e8-80ff-27aa2966f6af.png">

we define 3 different investing potential from low to high by sorted investing index percentile 3:4:3. A supervised multi-classes classification algorithm can be applied.

### Precision and Recall Testing
The Decision Tree gave the most promosing result. The overall accuracy is not high, but considering to our business goal, we only care the precision of Real Estate with high investment potencial (class 3 in this case). From this confusion matrix we identified that 23 samples are correctly identify, while only 3 Class 2 samples are mis-placed as class 3.

<img width="668" alt="screen shot 2018-03-21 at 11 49 01 pm" src="https://user-images.githubusercontent.com/15644582/37750727-f2432164-2d64-11e8-9cf2-589cc8b97c8b.png">

### Data Mapping
The map is based on Zip Codes areas in NYC and the color shows different level of investment potential. The scale arranges from 1 to 3. Deeper colors represent higher rental-to-sales ratios which consider as higher investment potential in this area. All neighborhoods have been remediated to correct Zip Codes areas.
 
<img width="760" alt="screen shot 2018-03-21 at 11 50 11 pm" src="https://user-images.githubusercontent.com/15644582/37750818-4078bec0-2d65-11e8-82bd-04f346e50315.png">

1. __Investment potential has increased but edged down recently.__ The existing data sample presented on the graph shows deeper filled areas in NYC from 2010 to 2014. But in 2016 the number of deep filled areas dropped which means relative rental price had an increasing trend
2. __Outside-of-center has higher potential.__ Most deep filled areas appear in boroughs except Manhattan which has proved that suburb areas in NYC has higher rental/sales ratio than the center.

3. __Queens and Bronx have most deep filled areas.__ On East Queens and North Bronx the ratios have remained high for several years on record.

