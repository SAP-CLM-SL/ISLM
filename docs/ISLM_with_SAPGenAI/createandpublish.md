# Create Intelligent Scenario

The Intelligent Scenarios app is used to create intelligent scenarios, review, and publish them, and to make them available in the Intelligent Scenario Management app.
In this step, you’ll create a new intelligent scenario to generate the order confirmation email for Sales Order using LLM model.

1. Open the Fiori Launchpad by clicking [here](https://44.219.212.100:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html#Shell-home) and launch **Intelligent Scenarios** app under **Analytics** tab. 
![](./images/Registration.png)<br>

2. Click the **Create** button and choose **Side-by Side**.
![](./images/Create.png) <br>

3. Provide the required information on the screen:
    - **Intelligent Scenario Name**: Enter a unique name starting with Z, such as `Z_SLS_ORD_CONF_###`, where ### is your attendee id mentioned in the cheat sheet.
    - **Intelligent Scenario Description**: `Generate sales order confirmation email`
    - **Intelligent Scenario Type**: `Generative AI` <br>
![](./images/NameDescriptionType.png)<br>
      
4. Select the **Usage Type** as **Stateless - With Embeddings**.<br> The usage type provides connectivity to GenAI Hub. For Stateless - With Embeddings usage type, the information or data from previous interactions with LLM is not retained. Each interaction is treated as a new request, ensuring a fresh context for every interaction. <br>
![](./images/UsageType.png)

5. Click the **Add Model** button.
![](./images/AddModel.png)

6. The **Add Generative AI Model** screen will pop up. Enter the below details:
    - **Name**: `Z_SLS_ORD_CONF_MDL`
    - **Description**: `LLM Model for generating SO email`
    - **Executable ID**: `azure-openai`
    - **Large Language Model Name**: `gpt-5-mini`
    - Optionally, choose a specific **Model Version** (latest is selected by default). In this case, we can keep as empty to have latest.
![](./images/ModelDetails.png)

7. Click the **Add** button.
![](./images/Add.png)

8. Click the **Add** prompt templates button to add **System prompt**.
![](./images/SPT.png)

9. In the Add **Prompt Template** dialog, enter the below details:
    - **Name**: `SYSTEM_PROMPT`
    - **Description**: `Provide context to gpt-5-mini model`
    - Select the **Display template information** as `Yes`
    - Enter the below **Prompt** text:
```
You are a sales executive who is responsible for reaching out to customers for confirming or declining their orders via email.
For the given sales order, evaluate the following:
1. Size of the delivery vehicle based on the number of items.
2. The distance between the source and destination location of delivery in kilometers.
3. The category of items which are ordered.

Write an email in the following format:
- The subject of email should be of format <Confirmation on order number: {order_number} placed on {booking_date}>
- The body of email should be of format: "Sales order contains <Category> to be delivered to <Location>. The order will be delivered via a <size> vehicle.
IF <distance between source address and delivery address> > 100 kms THEN include a message about potential delivery delays ELSE congratulate on being eligible for one day delivery
```
![](./images/SystemPrompt.png)

10. Click the **Save** button.
![](./images/Ssave.png)

11. Click the **Add** prompt templates button to add **User prompt**.
![](./images/UPT.png)

12. In the **Add Prompt Template** dialog, enter the below details:
    - **Name**: `USER_PROMPT`
    - **Description**: `Provide sales order item data for generating the order confirmation email`
    - Select the **Display template information** as `Yes`
    - Enter the below **Prompt** text:
```
Build a confirmation mail for a sales order containing {ISLM_Items}. The source address is {ISLM_Source} and the delivery address is {ISLM_Destination}.
```
![](./images/UserPrompt.png)

13. Click the **Save** button.
![](./images/Usave.png)

14. The added prompt should be visible in the Prompt Templates table. 
![](./images/Prompts.png)

15. Click the **Save Draft** button and navigate back to Intelligent Scenario by clicking the **back** button.
![](./images/DraftBack.png)

16. Scenario is now ready to be published. Click on **Publish** button. You will receive a message that Intelligent Scenario is published.
    ![](./images/Publish.png)

17. Search the Intelligent Scenario created by you by entering the **Intelligent Scenario name** and **Status = Published**.
    ![](./images/PIS.png)

Well done, you just created your first Side-by-side Intelligent Scenario.
