># Create and publish Intelligent Scenario

The Intelligent Scenarios app is used to create intelligent scenarios, review, and publish them, and to make them available in the Intelligent Scenario Management app. In this step, you’ll create a new intelligent scenario to predict the plane type using SAP BTP based ML service Data Attribute Recommendation.

Create a Prediction Class which defines the behavior of the scenario. Prediction class has methods to specify Inference type and ML Template for Data Attribute Recommendation. For this use case, we will use generic template which make use of Classification algorithm.

1. Open **SAP Logon** and logon to **S4H** system.
2. Open transaction `/nse24` and search for the ABAP class `ZCL_PLANTYPE_HO`. 
<img width="1167" height="485" alt="image" src="https://github.com/user-attachments/assets/a9e269b4-d581-46ab-a458-b72192b22649" />

3. Click the **Copy** button. 
<img width="1042" height="357" alt="image" src="https://github.com/user-attachments/assets/72a0560f-1b79-443b-85a2-989d08bcfa11" />

4. Provide the unique name in the **Copy to** field. Enter a unique name such as `ZCL_PLANTYPE_###`, where ### is your attendee id. And click the **tick** icon. 
<img width="1148" height="517" alt="image" src="https://github.com/user-attachments/assets/57d5a6df-fead-4896-a4a3-d62ee5cce23c" />

5. Click the **Local Object** button.
<img width="679" height="466" alt="image" src="https://github.com/user-attachments/assets/b7d2b024-7e06-417a-a4c2-fe07d82c8725" />

6. The class is created in **Inactive** status. Click the **Display** button. 
<img width="1323" height="365" alt="image" src="https://github.com/user-attachments/assets/a1884c9e-d24c-4057-a1c5-613d7b0d5b01" />

7. Click the **Activate** icon. 
<img width="1288" height="644" alt="image" src="https://github.com/user-attachments/assets/f9b25d59-2663-4285-985f-e233890be1fa" />

8. Click the **tick** icon. 
<img width="1646" height="1017" alt="image" src="https://github.com/user-attachments/assets/019fcef9-a99f-4a89-ab40-9bb2146111ff" />

9. Open the Fiori Launchpad by clicking [here](https://18.214.3.29:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#Shell-home). Click on the **Intelligent Scenario** app. 
<img width="1100" height="277" alt="image" src="https://github.com/user-attachments/assets/596ef7cd-845c-4d8f-9ab5-0a3d4976da3c" />

10. Click the **Create** button and choose **Side-by Side**.
This approach is commonly known as '**side-by-side**,' where the ML provider and the business application operate in separate stacks. 
<img width="1788" height="537" alt="image" src="https://github.com/user-attachments/assets/980dc32d-80d2-4000-b8d6-4a73267fa461" />

11. Provide the required information in the screen:
- **Intelligent Scenario Name**: Enter a unique name starting with Z, such as `Z_PRED_PLANETYPE_###`, where ### is your attendee id mentioned in the cheat sheet.
- **Intelligent Scenario Description**: `CLM Day Hands on 2025`
- **Intelligent Scenario Type**: `Data Attribute Recommendation` 
<img width="1869" height="655" alt="image" src="https://github.com/user-attachments/assets/dd89f7a6-bef3-46ad-b188-4a2268c2d698" />

12. Ensure the **Data Management checkbox** is selected. 
<img width="1888" height="660" alt="image" src="https://github.com/user-attachments/assets/22567c69-632b-4f01-8060-816977018db9" />

13. Click the value help for **Prediction Class**. 
<img width="1882" height="654" alt="image" src="https://github.com/user-attachments/assets/4edb9f49-6a80-477a-8bd1-d21b9d6c158f" />

14. Click the **OK** button in the information box. 
<img width="1858" height="658" alt="image" src="https://github.com/user-attachments/assets/85913ffc-9a21-414c-9c42-6aeba1e48f79" />

15. Click the **Add Model** button. The Add DAR Model dialog will pop up. Provide the following details:
- **Name**: `Z_PRED_PLANETYPE_MOD`
- **Description**: `Model for CLM Day 2025 - Hands on`
- **Training Dataset**: `Z_SFLIGHT_DATA` 
<img width="951" height="574" alt="image" src="https://github.com/user-attachments/assets/e011b817-61b4-4137-886e-695d525c96b4" />

16. Click the value help for the **Inputs** field. 
<img width="951" height="574" alt="image" src="https://github.com/user-attachments/assets/24d3b3d8-4e3a-44c4-ab7d-9f25be511b03" />

17. The **Select Model Inputs** dialog will pop up. Select all the Inputs expect `CARRID`, `CONNID`, `PLANETYPE`.
    **Tip**: Use the Select All option and uncheck the CARRID, CONNID, PLANETYPE. 
<img width="771" height="673" alt="image" src="https://github.com/user-attachments/assets/896161ed-cede-4788-bbb1-fc3b5370f6e6" />

18. Select the relevant **Machine Learning Provider Type** as `Category` or `Number`, as displayed in the screnshot. And click the **Select** button. 
<img width="763" height="667" alt="image" src="https://github.com/user-attachments/assets/4fecaec9-9a0c-424c-8049-2bc93fc276eb" />

19. Click the value help for the **Targets** field. 
<img width="945" height="574" alt="image" src="https://github.com/user-attachments/assets/1feabeba-1b60-4da9-9aec-ef45936804d1" />

20. The **Select Model Targets** dialog will pop up. Select `PLANETYPE` and the corresponding **Machine Learning Provider Type** as `CATEGORY`. And click the **Select** button.
<img width="765" height="691" alt="image" src="https://github.com/user-attachments/assets/69258068-4b4e-4bba-a3c8-c6ff8a48628f" />

21. Click the **Add** button. 
<img width="955" height="486" alt="image" src="https://github.com/user-attachments/assets/c4b62100-8308-4e62-9ed0-9403b0dfe438" />

22. The scenario is now created in **Draft** Status. You can view the input and output fields used to train the model in the **Input** and **Output** Tabs respectively. Also Scenario is now ready to be published.
Click on **Publish** button. You will receive a message that Intelligent Scenario is published. 
<img width="1903" height="864" alt="image" src="https://github.com/user-attachments/assets/23d3db35-ae85-463b-bfaa-c23770d251f3" />

23. Search the Intelligent Scenario created by you by entering the **Intelligent Scenario name** and **Status = Published**. 
<img width="1903" height="574" alt="image" src="https://github.com/user-attachments/assets/853d3ca9-2691-4a6a-a8cf-9d44ddf3498d" />

**Well done, you just created your first Side-by-side Intelligent Scenario.**
