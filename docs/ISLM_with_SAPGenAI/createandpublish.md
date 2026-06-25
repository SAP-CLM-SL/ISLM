# Create Intelligent Scenario

The Intelligent Scenarios app is used to create intelligent scenarios, review, and publish them, and to make them available in the Intelligent Scenario Management app.
In this step, you’ll create a new intelligent scenario to generate a summary and obtain key insights from Sales data using gpt-5 LLM model.

1. Open the browser and navigate to the Fiori Launchpad by clicking [here](https://ldai1ui3.wdf.sap.corp:44332/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-language=EN&sap-client=000#Shell-home). The login credentials are maintained [here](https://pages.github.tools.sap/engsrvperformance/dcom2025-genai-islm/exercises/credentials/). And launch the "Intelligent Scenarios" application.
2. Click the **Create** button and choose **Side-by-Side**.
3. Enter a unique Intelligent Scenario Name starting with Z: `Z_LLM_SCENARIO_### ` where ### is your attendee id.
4. Enter the below description in Intelligent Scenario Description field <br>
   `Summarize sales report`
5. Select the **Intelligent Scenario Type** as **Generative AI**.
6. Select the **Usage Type** as **Stateless - With Embeddings**. <br>
   The usage type provides connectivity to GenAI Hub. For Stateless - With Embeddings usage type, the information or data from previous interactions with LLM is not retained. Each interaction is treated as a new request, ensuring a fresh context for every interaction.
7. Click the **Add Model** button.
8. The Add Generative AI Model screen will pop up. Enter the below Name: `Z_SUMMARIZATION_MODEL`
9. Enter the below model Description<br>
`Model for analysis and summarization of sales data`
10. Select the Executable ID as azure-openai.


Well done, you just created your first Side-by-side Intelligent Scenario.
