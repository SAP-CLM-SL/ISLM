# Scenario storyline: Predict the plane type of an aircraft using Data Attribute Recommendation

## 1. Overview

In this exercise, we are going to predict the plane type of an aircraft using SAP BTP based ML service Data Attribute Recommendation. We will use the Intelligent Scenario Lifecycle Management (ISLM) framework to create and operate the ML use case. 

Data Attribute Recommendation uses machine learning to predict and classify data records.
With Data Attribute Recommendation you can
  -	Automate and speed up data management processes
  -	Reduce errors and manual efforts in data maintenance
  -	Increase data consistency and accuracy

This exercise includes the following steps: 
1. Create and publish an Intelligent Scenario.
2. Set up the connection for the Intelligent Scenario to connect to BTP based ML service.
3. Use Intelligent Scenario Management app to train, view model quality, deploy and activate the model.
4. View the inference result returned by the model in an ABAP report.

## 2. Create and publish Intelligent Scenario

The Intelligent Scenarios app is used to create intelligent scenarios, review, and publish them, and to make them available in the Intelligent Scenario Management app. In this step, you’ll create a new intelligent scenario to predict the plane type using SAP BTP based ML service Data Attribute Recommendation. 

Create a Prediction Class which defines the behavior of the scenario. Prediction class has methods to specify Inference type and ML Template for Data Attribute Recommendation. For this use case, we will use generic template which make use of Classification algorithm.

1. Open **SAP Logon** and logon to **S4H** system. Check the username and password provided in the cheat sheet.
2. Open transaction `/nse24` and search for the ABAP class `ZCL_PRED_PLANETYPE_000`.
![](./images/1.png)

3. Click the **Copy** button.
![](./images/2.png)

4. Provide the unique name in the **Copy to** field. Enter a unique name such as `ZCL_PRED_PLANETYPE_###`, where ### is your attendee id. And click the **tick** icon.
![](./images/3.png)

5. Click the **Local Object** button.
![](./images/4.png)

6. The class is created in **Inactive** status. Click the **Display** button.
![](./images/5.png)

7. Click the **Activate** icon.
![](./images/6.png)

8. Click the **tick** icon.
![](./images/7.png)

9. Open the Fiori Launchpad by clicking [here](https://18.214.3.29:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#Shell-home){:target="_blank"}. Input the username and password provided in the cheat sheet. Click on the **Intelligent Scenario** app.
![](./images/8.png)

10. Click the **Create** button and choose **Side-by Side**. <br/> This approach is commonly known as '**side-by-side**,' where the ML provider and the business application operate in separate stacks.
![](./images/9.png)

11. Provide the required information in the screen:
    - **Intelligent Scenario Name**: Enter a unique name starting with Z, such as `Z_PRED_PLANETYPE_###`, where ### is your attendee id mentioned in the cheat sheet.
    - **Intelligent Scenario Description**: `CLM Day Hands on 2025`
    - **Intelligent Scenario Type**: `Data Attribute Recommendation`
    - Ensure the `Data Management checkbox` is selected
![](./images/create1.png)

12. Ensure the **Data Management checkbox** is selected. ![](./images/create2.png)

13. Click the value help for **Prediction Class**.
![](./images/create3.png)

14. Click the **OK** button in the information box.
![](./images/create4.png)

15. Click the **Add Model** button. The Add DAR Model dialog will pop up. In the General Information section, provide the following details:
    - **Name**: `Z_PRED_PLANETYPE_MOD`
    - **Description**: `Model for CLM Day 2025 - Hands on`
    - **Training Dataset**: `Z_SFLIGHT_DATA`
![](./images/create15.png)

16. Click the value help for the **Inputs** field.
![](./images/create16.png)

17. The **Select Model Inputs** dialog will pop up. Select all the Inputs expect `CARRID`, `CONNID`, `PLANETYPE`. <br/> **Tip**: Use the Select All option and uncheck the CARRID, CONNID, PLANETYPE.
![](./images/create17.png)

18. Select the relevant **Machine Learning Provider Type** as `Category` or `Number`, as displayed in the screnshot. And click the **Select** button.
![](./images/create18.png)

19. Click the value help for the **Targets** field.
![](./images/create19.png)

20. The **Select Model Targets** dialog will pop up. Select `PLANETYPE` and the corresponding **Machine Learning Provider Type** as `CATEGORY`. And click the **Select** button.
![](./images/create20.png)

21. Click the **Add** button.
![](./images/create21.png)

22. The scenario is now created in **Draft** Status. You can view the input and output fields used to train the model in the **Input** and **Output** Tabs respectively. Also Scenario is now ready to be published.<br/> Click on **Publish** button. You will receive a message that Intelligent Scenario is published.
![](./images/create6.png)

23. Search the Intelligent Scenario created by you by entering the **Intelligent Scenario name** and **Status = Published**. 
![](./images/create7.png)

**Well done, you just created your first Side-by-side Intelligent Scenario.**

## 3. Set up the connection for Intelligent Scenario to connect to BTP based ML service

Once the Intelligent Scenario is published, we need to maintain the connection for the intelligent scenario in SAP S/4 HANA with the Data Attribute Recommendation service in BTP. This service has already been provisioned in BTP and  **service key** is available in the Desktop folder. 

1. Open transaction **/nSPRO** in **SAP Logon**<br>
   Click **SAP Reference IMG** 
   ![](./images/22.png)

2. Navigate to **ABAP Platform >Application Server >Basis Services >Intelligent Scenario Lifecycle Management> Service Connections for Machine Learning Infrastructure > Maintain Connection for an Intelligent Scenario**.Click on **Execute**
   ![](./images/23.png)

   ![](./images/24.png)

5. The ISLM Connection Mapping window opens. Click the **Create Connection** icon. 
   ![](./images/create14.png)

6. Input the Intelligent Scenario Name created by you and click on **Next**
   ![](./images/create8.png)

7. Enter the Service Key details. Please find the service key in a .txt file in desktop to get Service Key details.
   ![](./images/create9.png)

8. Click **Next**.
   ![](./images/create10.png)

9. Perform **Connection Check** to know the health of ML provider.
   ![](./images/create11.png)

10. Check the Connection Status changes to **Ready**. Click **Save**.
   ![](./images/create12.png)

11. New entry will be added to the table.
   ![](./images/create13.png)

### Well done, you just Set up the connection for Intelligent Scenario to connect to BTP based ML service.
<br>

## 4. Use Intelligent Scenario Management app to train, view model quality, deploy and activate the model
Once the Intelligent Scenario is published, the Intelligent Scenario Management app helps you to train, monitor the model quality, deploy, and activate the model for productive usage.
In this section, you will use the Intelligent Scenario Management app to perform ML operations. 

1. Open the Fiori Launchpad by clicking [here](https://44.207.24.229:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#Shell-home){:target="_blank"}. Input the username and password provided in the cheat sheet. Click on the **Intelligent Scenario Management** app.
   ![](./images/32.png)

2. Find the scenario created by searching using the name and navigate to the details page by clicking the **>** icon. 
   ![](./images/manage-1.png)

3. Select the Model and click on the **Train** button to launch the training dialog.
   ![](./images/manage-2.png)

4. Train dialog opens. To select a Version from the remote machine learning provider click on value help highlighted.
   ![](./images/manage-3.png)

5. Select the version 3.0 in the version field.
   ![](./images/manage-4.png)

6. Review the information in the train dialog. Click on Train.
   ![](./images/manage-5.png)

7. New Training will be created in Scheduled status.
   ![](./images/manage-6.png)

8. Monitor the status of Training and check that the status changes to Uploading Data.
    ![](./images/manage-18.png)

9. Monitor the status of Training and check the status changes to Training.
    ![](./images/manage-7.png)

10. Wait for the status of the Training to change to Completed. Note that training can take around 5 minutes to complete.
    ![](./images/manage-8.png)

11. Click on **>** icon to view Training Details.
    ![](./images/manage-9.png)

12. View the information in header section. 
    Click on **Debrief** tab.
    ![](./images/manage-10.png)

13. View Overall and target metrics in Debrief. **Accuracy, F1Score, Precision and Recall** are classification metrics. The higher the better.
    ![](./images/manage-10.png)

14. Click on Data Management tab to view details of data packets.
    ![](./images/manage-11.png)

15. Choose the back icon to navigate back to Trainings screen.
    ![](./images/manage-12.png)

16. Click on **Deploy** Button
    ![](./images/manage-13.png)

17. Click on **Deploy and Monitor** Button
    ![](./images/manage-14.png)

18. New Deployment will be created in Scheduled status.
    ![](./images/ScheduleDeployment.png)

19. Monitor the status of Deployment and check the status changes to Deployment Pending.
    ![](./images/manage-15.png)

20. Monitor the status of Deployment and check the status changes to **Deployed**. Note that Deployments can take 
    approximately **10 minutes** to be Deployed.
    ![](./images/manage-16.png)

21. To consume the resulting inference from this intelligent scenario the deployment must be activated. Select the Deployment and click on **Activate** button and choose **For All** 
    option. In the dialog Activate for All Users, choose **Activate For All**. Validate that the Deployment has **Active for 
    all** Indicator. Then the status will change to Active
    ![](./images/manage-17.png)


### Well done, you just used Intelligent Scenario Management app to train, view model quality, deploy and activate the model.
<br>
    
   
## 5. View the inference result returned by the model in an ABAP report
  In this step, you will use the ABAP GUI to view the inference result from the trained model.

   1. Open transaction **/nSE38** in the SAP GUI
      ![](./images/55.png)

   2. Input Report Name as `ZR_ISLM_TEST_OPERATION_API` and Click on **Execute** Button
      ![](./images/56.png)

   3. In the API Definition, choose option **TRIGGER_ONLINE_INFERENCE** from drop down.
      ![](./images/57.png)

   4. Enter the prediction class associated with your Intelligent Scenario (Created in Section 1 Step 3) .
      Click on **Execute**.
      ![](./images/58.png)

      Your trained model is now ready to predict the target **PLANETYPE**. To predict this target, inputs to model has to be provided.

      Copy the below text which contains the Inference Request with inputs in JSON format.
	- Inference Request contains the features and its value which is input for the trained model.
	- **topN**-parameter which defines how many options will be predicted.
      	- Inputs would be **FLDATE, PRICE, SEATSMAX, SEATSOCC, SEATSMAX_B, SEATSMAX_F, SEATSOCC_B, SEATSOCC_F, PAYMENTSUM, CURRENCY**.
      # Inference Request in JSON
```json
{
    "topN": 2,
    "objects": [
        {
            "objectId": "optional-identifier-5",
            "features": [
                {
                    "name": "FLDATE",
                    "value": ""
                },
                {
                    "name": "PRICE",
                    "value": "422.94"
                },
                {
                    "name": "SEATSMAX",
                    "value": "385"
                },
                {
                    "name": "SEATSOCC",
                    "value": "374"
                },
                {
                    "name": "SEATSMAX_B",
                    "value": "31"
                },
                {
                    "name": "SEATSMAX_F",
                    "value": "21"
                },
                {
                    "name": "SEATSOCC_B",
                    "value": "29"
                },
                {
                    "name": "SEATSOCC_F",
                    "value": "21"
                },
                {
                    "name": "PAYMENTSUM",
                    "value": ""
                },
                {
                    "name": "CURRENCY",
                    "value": ""
                }
            ]
        }
    ]
}
```
5. Paste the copied text in the **text editor**. Click on **tick** icon.
   ![](./images/59.png)
 
6. View the response from the trained model.

   In the response, you find the values that the model predicted. This includes the value that is predicted and the 
   probability. The probability describes how certain the model is about its prediction. **If the probability is close to 1, 
   the model is very certain**.
   
   Model predicts the PLANETYPE with two possible values(as defined in Inference request **"topN": 2** <br>
	| Predicted Value | Probability    | 
	| :---:   | :---: | 
	| A319-100 | 1.0 |
	| 747-400 | 0.0  |

   Note: The predicted values and the probabilities depend heavily on the inputs, the training data as well as the training metrics

   
   ![](./images/60.png)

### Well done, you just Viewed the inference result returned by the model in an ABAP report.

## 🎉 Congratulations! You have successfully completed the Exercise!🎉
