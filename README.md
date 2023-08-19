# Mercedes Car Prices
## Analyzing the Data
First of all, to get an overview of the dataset, I analyzed the characteristics of the first 5 vehicles, which include Year, Price, Mileage, Tax, Fuel Consumption and Engine Volume.

![1](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/885ff4ef-d477-4d3b-91cb-1f51f6f4ed63)

I also examined the general information of this data set. In this table, the Number, Mean, Standard Deviation and Minimum-Maximum values of the characteristics of the vehicles are the values that are important for me.

![2](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/46741bb3-0a69-41c1-b9f1-95075a31ffc5)

I then examined the distribution of the prices of the vehicles on the graph. I thought that the small number of high-priced vehicles and the fact that they were not normally distributed reduced the reliability of the data set.

![3](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/21a687f8-675a-4001-b3c8-453b12b4d25b)

I also examined the correlation of vehicle prices with other features. As can be seen here, the Mil feature seems to have the highest impact on vehicle prices. I also analyzed this on a graph.

![image](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/ae98a6f6-d32e-41fb-b285-65d385606f58)
![4](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/5daf43fb-2609-4454-bf7c-5b368f612d77)

## Correction of Data
First of all, I removed the anomalous distribution of the high-priced vehicles that first caught my eye. I removed the top 1% (131 vehicles) from the data set. Then I examined the new values together with the graph. I obtained a graph with a more normal distribution.

![2-1](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/b8abbad0-0131-4028-a0be-367e8a22837d)
![2-2](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/88ab8482-3068-4aaa-970d-43cacf4b602d)

I then listed the average prices of the vehicles by year and found that the prices increased from lower to higher models, as they should. However, there was an exception for 1970 vehicles. I removed that data from the data set.

![2-3](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/fd317b9c-4470-4d3a-a53a-c78ba2aef4f7)
![2-4](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/5bdd7d54-733b-4590-88e1-fdceac23519c)

## Creating the Model
First of all, I created a model consisting of 5 layers with 12 neurons (dense). I chose the regression approach of the model as ReLU.

![image](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/97c68e92-e59c-4789-a688-da40a1fc9f24)
![2-5](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/ced48924-dbec-47fe-b506-ca1bc4d8bd85)

Then I trained my model with batch_size=250 (data loading packet size), epochs=300 (number of times to rotate the data set).

## Evaluation of the Model
I examined the missing data in the training and the missing data in the data set on the graph. I saw that the lines are close to each other and gradually approaching zero, as they should be.

![3-1](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/5e00b4e3-a304-4b2d-8623-e202badf22f7)

I then made a new forecast with the data I had removed from the dataset for testing. I used a graph to observe how the new forecasts matched the actual prices. The green line in the middle shows what should happen. When I calculated the average margin of error, I found that prices varied by +/- £3137.

![3-2](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/2a95511e-e7e9-4319-9491-b577f9ff5491)

Then, as a final check, I had the price of a single vehicle estimated. The actual price of the vehicle was £65,980, but the estimate came to £63,644. This gives a margin of error of approximately 0.035.

![image](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/ee5728f2-00f6-4d45-a8e4-10469cfd3148)
![image](https://github.com/TolgaKilinckaya/mercedes_ml_price_predict/assets/119072606/613e21fd-8646-4ceb-8341-8442362848b1)
