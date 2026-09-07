# Create and publish Intelligent Scenario

The Intelligent Scenarios app is used to create intelligent scenarios, review, and publish them, and to make them available in the Intelligent Scenario Management app. In this step, you’ll create a new intelligent scenario to predict the plane type using SAP BTP based ML service Data Attribute Recommendation.

Create a Prediction Class which defines the behavior of the scenario. Prediction class has methods to specify Inference type and ML Template for Data Attribute Recommendation. For this use case, we will use generic template which make use of Classification algorithm.

1. Open **SAP Logon** and logon to **S4H** system.
2. Open transaction `/nse24` and search for the ABAP class `ZCL_PLANTYPE_HO`.
   ![](./images/1.png)

3. Click the **Copy** button.
   ![](./images/2.png)

4. Provide the unique name in the **Copy to** field. Enter a unique name such as `ZCL_PLANTYPE_###`, where ### is your attendee id. And click the **tick** icon.
   ![](./images/3.png)

5. Click the **Local Object** button.<br/>
   ![](./images/4.png)

6. The class is created in **Inactive** status. Click the **Display** button.
   ![](./images/5.png)

7. Click the **Activate** icon.
   ![](./images/6.png)

8. Click the **tick** icon.
   ![](./images/7.png)

9. Open the Fiori Launchpad by clicking [here](https://18.214.3.29:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#Shell-home){:target="\_blank"}. Click on the **Intelligent Scenario** app.
   ![](../ISLM_with_SAPGenAI/images/IntelligentScenariosApp.png)

10. Click the **Create** button and choose **Side-by Side**. <br/> This approach is commonly known as '**side-by-side**,' where the ML provider and the business application operate in separate stacks.
    ![](./images/9.png)

11. Provide the required information in the screen:
    - **Intelligent Scenario Name**: Enter a unique name starting with Z, such as `Z_PRED_PLANETYPE_###`, where ### is your attendee id mentioned in the cheat sheet.
    - **Intelligent Scenario Description**: `CLM Day Hands on 2025`
    - **Intelligent Scenario Type**: `Data Attribute Recommendation`
    ![](./images/create1.png)

12. Ensure the **Data Management checkbox** is selected.
![](./images/create2.png)

13. Click the value help for **Prediction Class**.
    ![](./images/create3.png)

14. Click the **OK** button in the information box.
    ![](./images/create4.png)

15. Click the **Add Model** button. The Add DAR Model dialog will pop up. Provide the following details:
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

20. The **Select Model Targets** dialog will pop up. Select `PLANETYPE` and the corresponding **Machine Learning Provider Type** as `CATEGORY`. And click the **Select** button.<br/>
    ![](./images/create20.png)

21. Click the **Add** button.
    ![](./images/create21.png)

22. The scenario is now created in **Draft** Status. You can view the input and output fields used to train the model in the **Input** and **Output** Tabs respectively. Also Scenario is now ready to be published.<br/> Click on **Publish** button. You will receive a message that Intelligent Scenario is published.
    ![](./images/create6.png)

23. Search the Intelligent Scenario created by you by entering the **Intelligent Scenario name** and **Status = Published**.
    ![](./images/create7.png)

**Well done, you just created your first Side-by-side Intelligent Scenario.**
