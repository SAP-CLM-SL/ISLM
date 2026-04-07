># Operating the Intelligent Scenario

Once the Intelligent Scenario is published, the Intelligent Scenario Management app helps you to train, monitor the model quality and activate the model for productive usage.

In this section, you will use the Intelligent Scenario Management app to perform ML operations.

1. Open the Fiori Launchpad by clicking [here](https://18.214.3.29:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#Shell-home). Click on the **Intelligent Scenario Management** app. 
<img width="1100" height="357" alt="image" src="https://github.com/user-attachments/assets/d8ccc167-1431-4a3c-af58-974fabdff0d6" />

2. Search the **First-Class Seats Occupied** scenario created by you and navigate to the details page by clicking the `>` icon. 
<img width="1919" height="381" alt="image" src="https://github.com/user-attachments/assets/a4d74ff5-245d-458e-936c-2b2ab28c6ef0" />

3. Select the Model and click on the **Train** button to trigger the training. 
<img width="1917" height="430" alt="image" src="https://github.com/user-attachments/assets/dcaf5c84-cc4e-40a5-9ac7-73420f63ddb1" />

4. In the Model section, view the Dataset Record Count. Click on **Train** button. 
<img width="1532" height="797" alt="image" src="https://github.com/user-attachments/assets/60689b1e-5de8-4f08-aebe-561f2bfa23a8" />

5. New Model Version will be created in **Scheduled** status. 
<img width="1919" height="600" alt="image" src="https://github.com/user-attachments/assets/5657c65b-4f3f-47dc-b21e-6bd6c1cef63b" />

6. Monitor the status of the **Model Version** and check the status changes to **Training**. 
<img width="1919" height="566" alt="image" src="https://github.com/user-attachments/assets/f8cab66a-8593-495e-b885-af11ac5d47ad" />

7. Monitor the status of the Model Version and check the status changes to **Ready**. 
<img width="1919" height="578" alt="image" src="https://github.com/user-attachments/assets/79d46ab1-5953-44e3-801b-d782bf126ff5" />

8. Click on '>' icon to view Model Version Report. 
<img width="1919" height="565" alt="image" src="https://github.com/user-attachments/assets/df8f35b6-2636-4c96-8fe4-7bc7d486deba" />

View different tabs like Quality Information and Debrief. You can see attributes about data quality and what key influencers are affecting the predictions.

Mean Absolute Error(MAE): Average absolute difference between the predicted values and the actual values. The lower the better.
Root Mean Square Error(RMSE): RMSE is the square root of mean squared error. It measures the average difference between values predicted by a model and the actual values. RMSE tells us how close the actual values are to prediction values made by the model. The lower the better.
Mean Absolute Percentage Error(MAPE) Average of the absolute percentage errors of the predictions. The lower the better. 

Choose the back icon  to navigate back to Model Versions screen.
Activate the model version to get the predictions from regression model. Select the Model Version and click the Activate button. 

Well done, you just Operated the Intelligent Scenario by training your first model.
