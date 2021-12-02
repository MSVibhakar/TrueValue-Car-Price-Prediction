# TRUE VALUE CAR PRICES :
Looking for new car : Yaaaa, we understand that increasing prices of the cars are a big problem in India for most of the middle class families , so TrueValue wanted to create a model that can predict the price of a used car , that would fit into the budget of middle class families in india . majority of the middle class family have family size of 4 and 6 including parents .

# Background:
Covid have badly impacted the worlds commute , there is no way to deny that. people have mostly preferred to travel in their own vehicels rather to take publictransport. In this Remarkable turn of events peopel from even middle class and lower middle class also started buying the cars . But, increasing the raw materials and production values have sky rocketed the price of cars , so all the these people now moved to buying an alredy used car , to maintain the commute and safty of their own families which brought boom in the sales of used cars which was alredy present in INDIAN MARKET.
**TRUEVALUE** is one of the popular choices for the all these car buyers. so they want to estimate on what base the value of the car can be decided , accpeting the fact that choices are different for all us influenced by the income , familysize , commute distence ..etc..

# Hypothesis:
For any one to buy a car, especially a used car there are some things that we take into considaration . condition of the car, how well maintained ,how years have passed 
, how many kilometers the car is run , how many owners it had , is the car still in production or do we get spares if we have any repiars to be done , how many seaters (4,6,7) , does it have any police cases ..etc.....
so with this in mind we are going to see how all the above factors are effecting the price of the car , a part from the it is mostly effected by the MontlyEMI and Brokersquote.

Steps that are carried out in the project :

 1. Loading the dataset 
 2. Understanding the data(shape ,size , keys ,datatypes, checking for duplicated values)
 3. Find unique values , Dealing the Null values 
 4. Correlation with the heatmaps with Seaborn 
 5. Outliers detecting and handeling
      * matplotlib and seaborn , box plots for outlier detection and kde plots for skewness 
      * Dealing the outliers by removing the unwanted records  
 6. Complete EDA,Observation,Analysis Report , Conclusion
 7. Feature Enginerring  ML-ModelBuilding
       * Standerd scaling ,Label encoding ,Extra tree regressor
       * Linear Regression ,lasso Regression ,XGB Regressor , Model Evaluation
       * RMSE,meansquare erroe,mean absolute error,performence of each model 
       * Randomized search cv
       * Hyperparameter tuning with Randomforest regressor
       * N-estimators and cv,msx_depth,sample_splt and leaf_split
       * Error evaluation 
 8. Importing a Pickel file  


# DATA ANLYTICS :

Our data is taken from 13 cities in india ,it includes 26 diffrent makeres, with both automaticn and manual transmissions and has 5 diffrent bodytypes like hatchback,sedan,suv,luxarysuv and luxarysedan with 182 diffrent model and 3 avialbilty sources 5 diffrent fuel types includes CNG,Electric,LPG.
Out of all Maruthi have the hihest number of cars , as per city Mumbai have higest number of cars, majority of petrol engines and manual trasmisson and rated great by TrueValue 
* WE have catagorized the cars on the basis of number of kilometers driven and number of years the car used and compred them with the salesprices, surprizigly the sales price of the  driven a lot  car is greater then the price of less driven car  which is as followes :

![download8](https://user-images.githubusercontent.com/85379601/144170593-73062e94-4a33-466c-89a5-6284d7112530.png),
![download18](https://user-images.githubusercontent.com/85379601/144355209-a4d8e3e7-efb6-4e99-94fa-0489211d628c.png)


AS we know the car price of car is dropped right the very moment it is purchased , we have calculted the price drop by each year and observed the price drop of the luxary sedan is low at 0.7% and highest for SUV at 2.5 % . 

![download9](https://user-images.githubusercontent.com/85379601/144170622-ee25ec0f-e43c-4a47-bf3a-af55c6e64282.png)

It remains to be same for the all the fuel types , price of the car kept declining over the years no matter how many kilometers it is driven :

![download4](https://user-images.githubusercontent.com/85379601/144171410-ef9f167a-6bcc-471e-9339-2e883faf736b.png)


Not only price dropped on the years used but also on the number of owners , most of the cars sold had 3 or 4 owners  for both manual automatic transmission :

![download6](https://user-images.githubusercontent.com/85379601/144171731-1aafd880-5bb0-4169-9d34-3583d6cdb285.png)

![download14](https://user-images.githubusercontent.com/85379601/144171792-91a22361-cd16-4971-a29e-b82e14fc9ae9.png)


Not only that , sales prices is also influened by the brand value of the makers , cars from benz , volvo , jeep ,audi,BMW, had good prices compared to brand like matruthi or tata Though they were moderatly driven Toyoto cars are the diven a lot cars on the list while Merc makes most of the revune  on sales but in comparision merc cars not the least driven cars it is datsun whos cars very less driven and soled for ver less prices. it is not just the number if kilometers  or number owners it had also the brand value of the car Infact it turned out be the major contributor in deciding the value if the car .

![download11](https://user-images.githubusercontent.com/85379601/144172560-50c23d93-6f68-4f61-bebe-65a9c4d13525.png)

![download10](https://user-images.githubusercontent.com/85379601/144172579-89f51a27-dd8e-41d3-984b-7162a1a18baa.png)
![download17](https://user-images.githubusercontent.com/85379601/144355133-a8e53d1d-a78a-4404-aa79-46e5cf7849ea.png)


But over all in genereal prices are deviating linearly as the number of years passed on lets understand it more better , take a look at the below graph drawn for the salesprice and kilomertes driven segregated by the catagories in legend (catagorized on the number if years used :

![download12](https://user-images.githubusercontent.com/85379601/144173086-b0e9cdf4-1e83-46b6-926c-666b77ee5980.png)
![download20](https://user-images.githubusercontent.com/85379601/144355058-abaa447e-72da-454e-b780-09a7aa7f8ca1.png)
![download21](https://user-images.githubusercontent.com/85379601/144355077-37af158a-bc32-497b-9197-03b81ff9b817.png)


Observe that :
* Most of the cars in the bracket of (0,200000) on x axis and (0,1) on y axis
* Also clearly observe that most of the blue datapoints are pointed towards that y axis and not much spread on x axis indicating that new cars less driven are having good price.
* observe the same with the orange and green datapoints ,orange points are linearly growing (most deviated to x axis ) indicating that price actually kept constant arounf 0.5le for certain intervel even numbers of kilometers kep increasing but at point of the car is driven 1 lack kilometers datapoints started coming down from 0.5 to 0.
* Contrastly for the old cars even the car is only less driven it did not have a high sale value and kept on decresing as the time passes on .

In comparion to the 3yr used car and 5yr used car though they might not have high number of kilomerters in their odometer 5yr old car had a less price also observing that some of the 8yr old car same price as the 3yr old car with more number of kilometers driven , this is because of the brand value of the car take a look below ; This graph is taken for the Hatchback bocy type and kilometer on x axis and price on y axis legend for 3yr and 8yr 

![download23](https://user-images.githubusercontent.com/85379601/144354994-cfdb187e-e415-465a-a611-212dc6ad056e.png)
![download24](https://user-images.githubusercontent.com/85379601/144355011-e2c40f6a-f6bb-4ff0-87e6-2193053200c4.png)
![download25](https://user-images.githubusercontent.com/85379601/144355020-6b18124b-1ca9-4f4a-9216-10de4196c52c.png)



Not only that EMI to be paied every month is the major contributor for all the middle class familes to purchase a car and that is the most importent factor effecting the saleprice (Below are top5 factors that are effecting sales price ) :

![image](https://user-images.githubusercontent.com/85379601/144176108-22866f55-1a80-4b42-a26e-227e07f7cd52.png)

Observe how perfectly it fits :

![image](https://user-images.githubusercontent.com/85379601/144176294-9c76f9e4-834c-44d8-b43d-31d6c6ec97cb.png)


Effect of all the variable ;

![download15](https://user-images.githubusercontent.com/85379601/144176226-dd822214-5dd1-4a2e-83de-50bcb1ec5a20.png)



# Conclusion:
Prices of the cars are generally depended on the number of years used and number of owners it has . but sales are also highly effected by the brandvalue of the cars 
though the count of cars sold in the luxary cars like BMW,benz,audi ,jeep are less they made more revenue compared to most of the highly sold cars .But as our target customers are mostly of middle class families who cant efford to buy and maintain a luxary cars, they need diffrent segment of the car . Hatchbacks are best offers 
though brands like maruthi,tata,hundai,toyoto,ford ,nissan, mahindra ..few more are less costly but have attracted huge number of customers out of all best fit would be a ***Hatchback type and manual transmission with a petrol engine not more then 6year old and with less number owners and price should be ranging between 4 to 6 lakhs.***


* ML models are present in the IPY.file :

After comapring the RMSE and MSE and MAE models it truned out the linearRegression is the best for the model evaluation 

* Error Distribution:

![image](https://user-images.githubusercontent.com/85379601/144176718-f2732ba4-ace6-4b38-92db-8752f303365c.png)











