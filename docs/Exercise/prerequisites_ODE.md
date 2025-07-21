### Add System to SAP Logon

1. Launch SAP Logon application on your computer.
   
2.	Click on **New** and select **Connection**, this action will open a dialog box for adding a new connection.
![](images/Add_Connection_ODE_1.png)
![](images/Add_Connection_ODE_2.png)

3. Search for **ODE** in the filter bar and click **Next**.
![](images/Add_Connection_ODE_3.png)

    
4. Select the public server and click **Next**.
![](images/Add_Connection_ODE_4.png)
<br/>

5. Verify the details as shown in the screenshot and click **Next**.
![](images/Add_Connection_ODE_5.png)
<br/>

6. Uncheck the **Activate Secure Network Communication** and click **Next**.
![](images/Add_Connection_ODE_8.png)
<br/>

7. Select Language as **Default** and click **Finish**
![](images/Add_Connection_ODE_7.png)
<br/>

Well done, you just added ODE system to your SAP Logon.
<br/>
<br/>

### Create Prediction Class
1. Launch SAP Logon application on your computer and login to ODE system.                  
Ctrl + Click [here](cheat_sheet.md) for login credentials.
  
2. In the **command** field, enter **SE24** transaction code.
![](images/Prediction_Class_create_0A.png)
  
3. In the initial screen of the Class Builder, enter the name of the class given below, and click on the **Copy** button. 
```
ZCL_SOC_EMAIL_CONFIRMATION_000
``` 
![](images/Prediction_Class_create_1.png)
       
    
4. A dialog box will appear prompting you to enter a new name for the copied class. Provide a unique name such as 
```
ZCL_SOC_EMAIL_CONFIRMATION_###
``` 
where ### is your attendee id. 
Click on the **Continue** button.
![](images/Prediction_Class_create_2.png)

5. A pop-up requesting transport and package details appears. Select **Local Object**.
![](images/Prediction_Class_create_5A.png)

6. Activate the new class by clicking the **Activate** button.
![](images/Prediction_class_create_4.png)

Well done, you just finished prerequisites and can start with the exercise - [Create a new Intelligent Scenario](create.md)
     
