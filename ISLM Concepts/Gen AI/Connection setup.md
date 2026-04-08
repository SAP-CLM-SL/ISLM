># Connection setup

Once the Intelligent Scenario is published, we need to maintain the connection for an intelligent scenario in SAP S/4 HANA with the Generative AI Hub service in BTP. Your service key is indicated in the cheat sheet that you received.

1. Logon to **S4H** system in **SAP GUI**.
2. Call up the transaction `/n ISLM_CONN_MAP` and Click the **Create Connection icon**. 
<img width="530" height="193" alt="image" src="https://github.com/user-attachments/assets/00a310c2-98d1-444c-982f-08f89548a420" />

3. Input the **Intelligent Scenario Name** and click on **Next** button. 
<img width="837" height="218" alt="image" src="https://github.com/user-attachments/assets/2493991c-78f6-46f5-a2f8-c5bf99fda9d0" />

4. Enter the **service key** from remote machine learning provider which is mentioned in the cheat sheet. And click the **Next** button. 
<img width="1097" height="622" alt="image" src="https://github.com/user-attachments/assets/e6a877de-ebce-4a40-8fdf-e04760e81537" />

5. The **RFC Destination** and **OAuth 2.0 Client Configuration** will be generated using the service key. 
<img width="926" height="462" alt="image" src="https://github.com/user-attachments/assets/d267bd45-6a34-4cc6-aa35-fb9179bd056d" />

6. Perform **Connection Check** to know the health of ML provider. 
<img width="926" height="461" alt="image" src="https://github.com/user-attachments/assets/fd1fa7b6-982a-42aa-ab61-9a0270594e87" />

7. Ensure that the Connection Status changes to **Ready**. Click the **Save** button. 
<img width="968" height="520" alt="image" src="https://github.com/user-attachments/assets/c2f0608f-f2a5-4a5e-83e6-787d4929c69e" />

8. A new entry will be added to the table. 
<img width="1877" height="294" alt="image" src="https://github.com/user-attachments/assets/2d624dbc-964e-47f1-b100-8054c4c42664" />


Well done, you just **Set up the connection for Intelligent Scenario** to connect to BTP based Generative AI Hub service.

<br></br>
<p>
  <a href="Create%20Intelligent%20Scenario.md">⬅️ Create Intelligent Scenario</a>
  
  <a href="ML%20Operations.md">ML Operations ➡️</a>
</p>
