# ShellDatathon
This repo contains the work me and my partner have done for the 2022/2023 Shell Datathon Competition
https://www.kaggle.com/competitions/shell-datathon-coderspace/overview

*Note: I have used Git LFS to store the large .pkl data files so I could push the commits

The aim of this datathon is to predict the weekly fuel orders across Shell Turkey's 1000+ stations in the year 2019. 
Participants have access to the price data for 2014-2019, and sales data for 2014-2018.
Publicly available external datasets can be used.
The evaluation is by RMSLE scores of the prediction.

Our approach:
Data preparation:
- Make the necessary changes to the provided training dataset, so we have a single unified dataset with total weekly orders, price and location data
- Gather external data to represent:
  - Economic factors
      -USD/TRY WoW change : for price rise anticipation
      -GDP QoQ Growth: Economic Health
      -Inflation since December the previous year: Fall in real incomes as wages typically adjust every January
      -Trailing 12m new car registration: More cars more fuel
      -Public holidays in the upcoming week: Holidays see spikes in usage
- Add extra features using existing data
  - Past sales (-51/52/53/54 weeks)
  - Season
  - Week of Year
  - One Hot Encoded Country Region
  - Price at past week
 
 
 ML Model:
 - We have tried fitting a Dense Neural Network with Tensorflow to achieve a peak RMSLE error of ~2.85 on the test data
      
  
