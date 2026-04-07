># Visualizing Model Version Predictions

1. Open the Fiori Launchpad by clicking [here](https://18.214.3.29:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#Shell-home). Click on the **Intelligent Scenario** app. 
<img width="1100" height="277" alt="image" src="https://github.com/user-attachments/assets/83825c73-3e98-4916-8a1b-f8ba02248f70" />

2. Search the Intelligent Scenario created by you by entering the **Intelligent Scenario name** as `Z_SEATOCC_FTCLAS_###`, where ### is your attendee id and **Status = Published**. Navigate to the details page by clicking the `>` icon. 
<img width="1847" height="519" alt="image" src="https://github.com/user-attachments/assets/e5b0ef51-df39-4d57-93bd-797ea726f759" />

3. Click on **Apply Setting** Tab. You can find the 3 Apply CDS views in this tab. We can see the predictions for each view in next steps. 
<img width="732" height="474" alt="image" src="https://github.com/user-attachments/assets/8f5a5618-e573-40ab-9455-e72cf5a7a956" />

4. You will use the SAP GUI to view the model's prediction. Login to **S4H/100** system via SAP GUI. Type /n se38 in the command field and press **ENTER**. 
<img width="1174" height="331" alt="image" src="https://github.com/user-attachments/assets/c1fa0969-0523-4eec-90ed-0f6b6e822152" />

5. Search for report **RUT_DDLS_DATA_PREVIEW** and click on **Execute(F8)**. 
<img width="1453" height="835" alt="image" src="https://github.com/user-attachments/assets/310238c2-41cf-446c-8d8f-02f5e83eaca4" />

6. Enter the ISLM generated 1st CDS view of created Intelligent Scenario to view predictions from trained model.
CDS View will have following name `Z_SEATOCC_FTCLAS_###_CDS01`, where ### is your attendee id.
Enter CDS View Name in Entity Name field and click on **Execute**. 
<img width="1914" height="970" alt="image" src="https://github.com/user-attachments/assets/14af3f20-5553-4c81-9b36-fbd80fc5bdfd" />

7. You can scroll down and see the model's keys in the first four columns: **Airline Code, Flight Connection Number, Flight Date and Booking number**.
Column **SEATSOCCF** has the actual value of the seats occupied.
Column **GB_SCORE_SEATSOCCF** column has the predicted value of the occupied seats. 
<img width="1383" height="1033" alt="image" src="https://github.com/user-attachments/assets/6edf3d1f-dc0d-4308-87f1-f1586068350c" />

8. Goto **SE38** again and Search for report **RUT_DDLS_DATA_PREVIEW** and click on **Execute(F8)**. Enter the ISLM generated 2nd CDS view of created Intelligent Scenario to view predictions from trained model.
CDS View will have following name `Z_SEATOCC_FTCLAS_###_CDS01_KEY`, where ### is your attendee id.
Enter CDS View Name in Entity Name field and click on **Execute**. 
<img width="1909" height="957" alt="image" src="https://github.com/user-attachments/assets/b84d9111-8d8a-4591-9c8e-3147c45f57db" />

9. Provide below values to the respective CDS parameters:
- P_BOOKID = `2274`
- P_CARRID = `AZ`
- P_CONNID = `555`
- P_FLDATE = `20250813`
  <img width="1091" height="782" alt="image" src="https://github.com/user-attachments/assets/1c437009-5b57-40be-9c25-69c920dcb93f" />

10. You can scroll down and see the model's keys in the first four columns: **Airline Code, Flight Connection Number, Flight Date and Booking number**.
Column **SEATSOCCF** has the actual value of the seats occupied.
Column **GB_SCORE_SEATSOCCF** column has the predicted value of the occupied seats. 
<img width="1432" height="302" alt="image" src="https://github.com/user-attachments/assets/0dd11ed7-9fb3-4ffc-a788-a4d063ae7c88" />

11. Goto **SE38** again and Search for report **RUT_DDLS_DATA_PREVIEW** and click on **Execute(F8)**. Enter the ISLM generated 3rd CDS view of created Intelligent Scenario to view predictions from trained model.
CDS View will have following name `Z_SEATOCC_FTCLAS_###_CDS01_WHR`, where ### is your attendee i.
Enter CDS View Name in Entity Name field and click on Execute. 
<img width="1909" height="993" alt="image" src="https://github.com/user-attachments/assets/dd7f923e-0e73-4911-9b07-b407174d00d5" />

12. Provide below values to the respective CDS parameters
- P_WHERE = `CONNID = 0017 AND FLDATE = 20250813`
<img width="1094" height="782" alt="image" src="https://github.com/user-attachments/assets/5eec33c5-ba42-4d06-b545-9c3092c4ca6b" />

13. You can scroll down and see the model's keys in the first four columns: **Airline Code, Flight Connection Number, Flight Date and Booking number**.
Column **SEATSOCCF** has the actual value of the seats occupied.
Column `GB_SCORE_SEATSOCCF` column has the predicted value of the occupied seats. 
<img width="1391" height="1025" alt="image" src="https://github.com/user-attachments/assets/8bb5faab-1b68-4b85-8b06-55c8bf344e99" />

**Well done, you just visualized your trained model predictions..!**
