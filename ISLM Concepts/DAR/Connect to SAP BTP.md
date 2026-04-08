># Set up the connection for Intelligent Scenario to connect to BTP based ML service

Once the Intelligent Scenario is published, we need to maintain the connection for the intelligent scenario in SAP S/4 HANA with the Data Attribute Recommendation service in BTP. This service has already been provisioned in BTP and **service key** is available in the Cheat sheet.

1. Open transaction **/nSPRO** in **S4H** system via **SAP Logon**. And click **SAP Reference IMG** button. 
<img width="1202" height="718" alt="image" src="https://github.com/user-attachments/assets/4c2608c1-fc36-4909-be85-0307697d0cc7" />

2. Navigate to **ABAP Platform >Application Server >Basis Services >Intelligent Scenario Lifecycle Management> Service Connections for Machine Learning Infrastructure > Maintain Connection for an Intelligent Scenario**. 
<img width="1242" height="910" alt="image" src="https://github.com/user-attachments/assets/5d802b56-9bee-43b6-b9fa-733f276be7e1" />

3. Click the **Execute** button.
<img width="1190" height="882" alt="image" src="https://github.com/user-attachments/assets/a9d82465-8f3f-4b21-9393-aeb26ccd7f8e" />

4. In the ISLM Connection Mapping screen, click the **Create Connection** icon. 
<img width="1918" height="373" alt="image" src="https://github.com/user-attachments/assets/13167a57-fa95-4fd0-b668-1b35c8ea5b3f" />

5. Input the Intelligent Scenario Name created by you (`Z_PRED_PLANETYPE_###`, where ### is your attendee id) and click the **Next** button. 
<img width="1117" height="375" alt="image" src="https://github.com/user-attachments/assets/5b359adf-9b47-4e83-a48c-da4e24e82bfa" />

6. Enter the **Service Key** maintained in the cheat sheet. 
<img width="1459" height="937" alt="image" src="https://github.com/user-attachments/assets/12f22378-96c7-484d-bb2e-b5f45117fe78" />

7. Click the **Next** button. 
<img width="1459" height="937" alt="image" src="https://github.com/user-attachments/assets/482453eb-d62c-4d44-a670-f3bedcbcb7b5" />

8. Perform **Connection Check** to know the health of ML provider. 
<img width="1237" height="694" alt="image" src="https://github.com/user-attachments/assets/9b59a1ff-88f3-47b3-968d-852fecb697ca" />

9. Ensure that the **Connection Status** changes to **Ready**. Click the **Save** button. 
<img width="1242" height="699" alt="image" src="https://github.com/user-attachments/assets/a4a823dd-24e1-4233-b732-076b43d45b6b" />

10.A new entry is added to the table. 
<img width="1897" height="406" alt="image" src="https://github.com/user-attachments/assets/e942f56f-56cb-418c-98a8-a45b35afeb20" />

**Well done, you just Set up the connection for Intelligent Scenario to connect to BTP based ML service.**
<br></br>
<p>
  <a href="Create%20Intelligent%20Scenario.md">⬅️ Create Intelligent Scenario</a>
  
  <a href="ML%20Operations.md">ML Operations ➡️</a>
</p>
