># Create Intelligent Scenario

The Intelligent Scenarios app is used to create intelligent scenarios, review, and publish them, and to make them available in the Intelligent Scenario Management app.

In this step, you’ll create a new intelligent scenario to predict the airplane seats occupation in the first class of a flight using SAP HANA ML algorithm.

For this use case we will use regression model with Gradient Boosting algorithm.

SAP HANA APL lets you build and apply different types of predictive models, such as classification, regression, and time series forecasting models.

Gradient Boosting regression model type provides a more accurate modeling result than the legacy regression model.

1. Open the Fiori Launchpad by clicking [here](https://18.214.3.29:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#Shell-home). Click the **Intelligent Scenario** app.
   <img width="1100" height="277" alt="image" src="https://github.com/user-attachments/assets/de1e7553-1689-4aa8-b086-4eb5a6b999e1" />

2. Click the **Create** button and choose **Embedded**.
In Embedded approach, a business application, for example SAP S/4HANA runs in the same stack as its machine learning provider SAP HANA ML and it provides analytics libraries **SAP HANA Automated Predictive Library (APL)** or **SAP HANA Predictive Analysis Library (PAL)**.
<img width="1838" height="867" alt="image" src="https://github.com/user-attachments/assets/115b0d3f-59b1-446d-81fe-0ef6ca0a577a" />

3. Click the **Do Not Show Again and Close** button in the Onboarding Dialog. 
<img width="1746" height="911" alt="image" src="https://github.com/user-attachments/assets/a641094c-4fe4-43c7-88cf-45714be1e0c4" />

4. Provide the required information in the screen:

5. **Intelligent Scenario Name:** Enter a unique name starting with Z, such as `Z_SEATOCC_FTCLAS_###`, where ### is your attendee id.
6. **Intelligent Scenario Description**: `Predict seats occupied in the first class of a flight.`
7. **Intelligent Scenario Type:** Select `Regression` type.
8. **Algorithm**: Select `Gradient Boosting`.
9. **Machine Learning Library**: Select `APL`. 
<img width="1751" height="647" alt="image" src="https://github.com/user-attachments/assets/07758a52-580c-44b7-afa8-8e8f74d035db" />

10. Click the **Add Model** button. 
<img width="1751" height="647" alt="image" src="https://github.com/user-attachments/assets/f2f010de-b56f-425b-aaf7-e25d4f64369c" />

11. The APL Regression Model screen will pop up. Provide information as mentioned below:

12. **Name**: Enter a model name starting with Z - `ZISLM_SFLIGHT_TRAIN_CDS_MODEL`.
13. **Description:** Enter the description - `Flight model`.
14. **Training Dataset:** `Z_SFLIGHTTRAINCDS`. Training Dataset to be used for training the model.
15. **Apply Dataset**: `Z_SFLIGHTPREDICTCDS`. Apply dataset is Dataset used for prediction.
    Note that apply dataset is different from training dataset.
16. **Target**: `SEATSOCCF`. Target variable is field whose value you want to predict.
17. **Max Reason Code**: `1` Number of reason codes you want to generate.
Reason codes are variables whose values have the most influence in a score-based decision (typically a risk score). The variables for which the contribution is the most influential are selected as the most important reason codes.
Apply output configuration has the selected metrics that are added in the intelligent scenario output and used for prediction. 
<img width="958" height="785" alt="image" src="https://github.com/user-attachments/assets/65795d40-0efc-4f32-bef8-f4f277831690" />

18. Click the **Add** button. 
<img width="958" height="785" alt="image" src="https://github.com/user-attachments/assets/6e88764a-ebf6-46ad-a63e-b3e52c7fdd36" />

19. The scenario is now created in **Draft** Status. 
<img width="1736" height="850" alt="image" src="https://github.com/user-attachments/assets/16e3afb4-fda6-4cf9-969a-5c672697d43a" />

20. View the **Input Tab** which displays the **Key, Input**, and **Target** fields.
The Input variable is considered for modelling.
The Key variable is a key field of the dataset and is also considered for modelling.
The Target variable is the variable whose values are to be modelled and predicted by other variables. 
<img width="1736" height="850" alt="image" src="https://github.com/user-attachments/assets/c5a0a656-455e-4f36-9e92-705897a61dd2" />

21. View the **Output tab** which displays the **Key, Target**, and **Prediction** fields.
The Prediction variable includes the calculated result. 
<img width="1736" height="850" alt="image" src="https://github.com/user-attachments/assets/2ad28f67-9221-41ed-985f-0204744d0e43" />

22. Scenario is now ready to be published. Click on **Publish** button. You will receive a message that Intelligent Scenario is published. 
<img width="1911" height="1025" alt="image" src="https://github.com/user-attachments/assets/85144a45-6d0b-497f-ae02-063ea556f65c" />

23. Search the Intelligent Scenario created by you by entering the **Intelligent Scenario name** as `Z_SEATOCC_FTCLAS_###`, where ### is your attendee id and **Status = Published**. Navigate to the details page by clicking the > icon. 
<img width="1847" height="519" alt="image" src="https://github.com/user-attachments/assets/3b57e9cf-fda6-424b-ae04-29e12e174af9" />

24. Click on **Apply Setting** Tab. Three CDS views are generated for the intelligent scenario to allow easy access to the predictions. Click the i icon to view the functionality & usage of each CDS view. 
<img width="1042" height="477" alt="image" src="https://github.com/user-attachments/assets/fa012cc9-c39a-4b73-9160-1f9ddac76b98" />

Well done, you just created your first embedded Intelligent Scenario.
