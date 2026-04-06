># Create Intelligent Scenario

The Intelligent Scenarios app is used to create intelligent scenarios, review, and publish them, and to make them available in the Intelligent Scenario Management app. In this step, you’ll create a new intelligent scenario to generate the order confirmation email for Sales Order using LLM model.

1. Open **SAP Logon** and logon to **S4H** system.
2. Create a Prediction Class which defines the behavior of the scenario. Prediction class has methods to specify Inference type and metadata like end point URI for LLM Model.
Open transaction `/nse24` and search for the class `ZCL_SOC_EMAIL_CONFIRMATION`
<img width="925" height="362" alt="image" src="https://github.com/user-attachments/assets/4c6b48f0-572e-4894-a2b0-21b88736c83d" />

3. Click the **Copy** button. 
<img width="925" height="362" alt="image" src="https://github.com/user-attachments/assets/4338cd37-7030-44ed-9233-b12371cd6199" />

4. Provide the unique name in the **Copy to** field. Enter a unique name starting with `ZCL`, such as `ZCL_SLS_ORD_CONF_###`, where ### is your attendee id mentioned in the cheat sheet. And click the **tick icon**. 
<img width="925" height="445" alt="image" src="https://github.com/user-attachments/assets/013bb0c4-0a8e-43ac-b8ae-f86f279a8dad" />

5. Click the **Local Object** button.
<img width="925" height="445" alt="image" src="https://github.com/user-attachments/assets/95d35a1b-f8da-471c-8022-5cc37a46e356" />
 
6. The class is created in **Inactive** status. Click the **Display** button.
<img width="826" height="300" alt="image" src="https://github.com/user-attachments/assets/9368814d-78c3-470c-a2bb-70c1cdb4da47" />

7. View the following methods of the prediction class.
8. **IF_ISLM_INTS~GET_INFERENCE_TYPE:** Using this method, specify the inference type that supports this intelligent scenario.
9. **IF_ISLM_INTS_SBS_DAR~GET_SERVEFLOW_ENDPOINT_URI:** Using this method, specify the end point URI of the LLM Model.
<img width="1374" height="550" alt="image" src="https://github.com/user-attachments/assets/e71dff6f-86bb-4e05-8030-965503830e21" />

10. Click the **Activate** icon. 

11. Click the **tick** icon.
<img width="1140" height="745" alt="image" src="https://github.com/user-attachments/assets/b2b4b949-eb83-4e33-bbaa-784e080a0266" />

12.Open the Fiori Launchpad by clicking [here](https://18.214.3.29:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#Shell-home).

Click on **Intelligent Scenario Management section** and choose the **Intelligent Scenarios app**.
<img width="1100" height="277" alt="image" src="https://github.com/user-attachments/assets/b7844c99-abb8-4f36-9bde-70d166df5510" />

13. Click the **Create** button and choose **Side-by Side**.
<img width="1215" height="365" alt="image" src="https://github.com/user-attachments/assets/3224453f-d581-49fd-8733-d988d713540b" />

14. Provide the required information in the screen:
- **Intelligent Scenario Name:** Enter a unique name starting with Z, such as `Z_SLS_ORD_CONF_###', where ### is your attendee id mentioned in the cheat sheet.
- **Intelligent Scenario Description:** `Generate sales order confirmation email`
- **Intelligent Scenario Type:** `Generative AI`
<img width="1215" height="365" alt="image" src="https://github.com/user-attachments/assets/7547c4ea-c2da-4b48-b542-d28c685d3a5a" />

15. Select **Prediction Class** from value help. 
<img width="1791" height="600" alt="image" src="https://github.com/user-attachments/assets/5e5cd038-0728-4c15-a6ab-a05308407c45" />

16. Select the **prediction class** created by you in the previous section. 
<img width="1791" height="600" alt="image" src="https://github.com/user-attachments/assets/6a41af05-efd8-4e76-b0c1-b3468927f94c" />

Click the Add Model button. 

The Add Generative AI Model screen will pop up. Enter the below details:

Name: Z_SLS_ORD_CONF_MDL
Description: LLM Model for generating SO email
Executable ID: azure-openai
Large Language Model Name: gpt-4o-mini 
Click the Add button. 

Click the Add prompt templates button. 

In the Add Prompt Template dialog, enter the below details:

Name: SYSTEM_PROMPT
Description: Provide context to gpt-4o-mini model 
Enter the Prompt text:


You are a sales executive who is responsible for reaching out to customers for confirming or declining their orders via email.
For the given sales order, evaluate the following:
1. Size of the delivery vehicle based on the number of items.
2. The distance between the source and destination location of delivery in kilometers.
3. The category of items which are ordered.

Write an email in the following format:
- The subject of email should be of format <Confirmation on order number: {order_number} placed on {booking_date}>
- The body of email should be of format: "Sales order contains <Category> to be delivered to <Location>. The order will be delivered via a <size> vehicle.
IF <distance between source address and delivery address> > 100 kms THEN include a message about potential delivery delays ELSE congratulate on being eligible for one day delivery

Click the Save button. 

Click the Add prompt templates button. 

In the Add Prompt Template dialog, enter the below details:

Name: USER_PROMPT
Description: Provide sales order item data for generating the order confirmation email 
Enter the Prompt text:


Build a confirmation mail for a sales order containing {ISLM_Items}. The source address is {ISLM_Source} and the delivery address is {ISLM_Destination}.

Click the Save button. 

The added prompt should be visible in the Prompt Templates table. Click the Save Draft button. 

Navigate back to Intelligent Scenario by clicking the back button. 

Scenario is now ready to be published. Click on Publish button. You will receive a message that Intelligent Scenario is published. 

Search the Intelligent Scenario created by you by entering the Intelligent Scenario name and Status = Published. 

Well done, you just created your first Side-by-side Intelligent Scenario.
