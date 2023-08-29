- There are three error metrics that are commonly used for evaluating and reporting the performance of a regression model; they are: Mean Squared Error (MSE). Root Mean Squared Error (RMSE). Mean Absolute Error (MAE)
- MSE : The mean squared error measures the average of the squares of the errors.
```
from sklearn.metrics import mean_squared_error
mse = mean_squared_error(df['y'], df['y_predicted'])
print(mse)
```
![image](https://github.com/Kkumar-20/Data_Scientist/assets/96828026/f4782d43-9b53-49fa-afc5-03fa8ca740dd)
- RMSE, which is the square root of the average squared distance (difference between actual and predicted value). RMSE is defined as the square root of all the squares of the distance divided by the total number of points.
![image](https://github.com/Kkumar-20/Data_Scientist/assets/96828026/80068521-8d16-4b91-8286-7eff74a336b1)
![image](https://github.com/Kkumar-20/Data_Scientist/assets/96828026/5aa3f8f6-59f8-499b-b4ea-06ec4db9734e)
- The MAE is simply defined as the sum of all the distances/residual s(the difference between the actual and predicted value) divided by the total number of points in the dataset.
- - It is the absolute average distance of our model prediction.
![image](https://github.com/Kkumar-20/Data_Scientist/assets/96828026/1623c6f6-6199-434f-b705-a24b56d92402)
![image](https://github.com/Kkumar-20/Data_Scientist/assets/96828026/420f4149-3e96-4a19-94c2-215bf83812b0)
- RMSE is the most famous evaluation metric for the regression model. The overall calculation of RMSE is similar to MSE; the final value is square-rooted as we calculated the square of errors in MSE.
- The R2 score (pronounced R-Squared Score) is a statistical measure that tells us how well our model is making all its predictions on a scale of zero to one.
![image](https://github.com/Kkumar-20/Data_Scientist/assets/96828026/ea61c734-bab4-4143-af27-6a53e1a3accd)
