# Visualizing Model Version Predictions

1. Open the Fiori Launchpad by clicking [here](https://18.214.3.29:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#Shell-home){:target="\_blank"}. Click on the **Intelligent Scenario** app.
![](../ISLM_with_SAPGenAI/images/IntelligentScenariosApp.png)

2. Search the Intelligent Scenario created by you by entering the **Intelligent Scenario name** as `Z_SEATOCC_FTCLAS_###`, where ### is your attendee id and **Status = Published**. Navigate to the details page by clicking the `>` icon.
![](./images/SearchScenario.png)

3. Click on **Apply Setting** Tab. You can find the 3 Apply CDS views in this tab. We can see the predictions for each view in next steps.
![](./images/ViewApplyViews.png)

4. You will use the SAP GUI to view the model's prediction. Login to **S4H/100** system via SAP GUI. Type `/n se38` in the command field and press **ENTER**.
![](./images/28.png)

5. Search for report **RUT_DDLS_DATA_PREVIEW** and click on **Execute(F8)**.
![](./images/29.png)

6. Enter the ISLM generated 1st CDS view of created Intelligent Scenario to view predictions from trained model. <br/> CDS View will have following name `Z_SEATOCC_FTCLAS_###_CDS01`, where ### is your attendee id. <br/> Enter CDS View Name in Entity Name field and click on **Execute**.
   ![](./images/30.png)

7. You can scroll down and see the model's keys in the first four columns: **Airline Code, Flight Connection Number, Flight Date and Booking number.** <br/>Column **SEATSOCCF** has the actual value of the seats occupied. <br/>Column **GB_SCORE_SEATSOCCF** column has the predicted value of the occupied seats.
   ![](./images/PredictionsFromMainView.png)

8. Goto **SE38** again and Search for report **RUT_DDLS_DATA_PREVIEW** and click on **Execute(F8)**. Enter the ISLM generated 2nd CDS view of created Intelligent Scenario to view predictions from trained model.<br/> CDS View will have following name `Z_SEATOCC_FTCLAS_###_CDS01_KEY`, where ### is your attendee id. <br/>Enter CDS View Name in Entity Name field and click on **Execute**.
   ![](./images/32.png)

9. Provide below values to the respective CDS parameters:
    - P_BOOKID = `2274`
    - P_CARRID = `AZ`
    - P_CONNID = `555`
    - P_FLDATE = `20250813`
    ![](./images/EnterKeyParameters.png)

10. You can scroll down and see the model's keys in the first four columns: **Airline Code, Flight Connection Number, Flight Date and Booking number.** <br/> Column **SEATSOCCF** has the actual value of the seats occupied. <br/> Column **GB_SCORE_SEATSOCCF** column has the predicted value of the occupied seats.
    ![](./images/PredictionFromKeyView.png)

11. Goto SE38 again and Search for report **RUT_DDLS_DATA_PREVIEW** and click on Execute(F8). Enter the ISLM generated 3rd CDS view of created Intelligent Scenario to view predictions from trained model. <br/> CDS View will have following name `Z_SEATOCC_FTCLAS_###_CDS01_WHR`, where ### is your attendee i. <br/> Enter CDS View Name in Entity Name field and click on **Execute**.
    ![](./images/35.png)

12. Provide below values to the respective CDS parameters 
    - P_WHERE = `CONNID = 0017 AND FLDATE = 20250813`
    ![](./images/EnterWhereParameter.png)

13. You can scroll down and see the model's keys in the first four columns: **Airline Code, Flight Connection Number, Flight Date and Booking number.** <br/> Column **SEATSOCCF** has the actual value of the seats occupied. <br/> Column **GB_SCORE_SEATSOCCF** column has the predicted value of the occupied seats.
    ![](./images/PredictionsFromWhereView.png)

**Well done, you just visualized your trained model predictions..!**
