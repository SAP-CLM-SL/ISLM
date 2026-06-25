# Create Intelligent Scenario

The Intelligent Scenarios app is used to create intelligent scenarios, review, and publish them, and to make them available in the Intelligent Scenario Management app.
In this step, you’ll create a new intelligent scenario to generate a summary and obtain key insights from Sales data using gpt-5 LLM model.

1. Open the browser and navigate to the Fiori Launchpad by clicking [here](https://ldai1ui3.wdf.sap.corp:44332/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-language=EN&sap-client=000#Shell-home). The login credentials are maintained [here](https://pages.github.tools.sap/engsrvperformance/dcom2025-genai-islm/exercises/credentials/). And launch the "Intelligent Scenarios" application.
2. Click the **Create** button and choose **Side-by-Side**.
3. Provide the required information on the screen:
    - **Intelligent Scenario Name**: Enter a unique name starting with Z, `Z_LLM_SCENARIO_### ` where ### is your attendee id.
    - **Intelligent Scenario Description**: `Summarize sales report`
    - **Intelligent Scenario Type**: `Generative AI`
4. Select the **Usage Type** as **Stateless - With Embeddings**. <br>
   The usage type provides connectivity to GenAI Hub. For Stateless - With Embeddings usage type, the information or data from previous interactions with LLM is not retained. Each interaction is treated as a new request, ensuring a fresh context for every interaction.
5. Click the **Add Model** button.
6. The Add Generative AI Model screen will pop up. Enter the below Name: `Z_SUMMARIZATION_MODEL`
7. Enter the below model **Description**: `Model for analysis and summarization of sales data`
8. Select the **Executable ID** as **azure-openai**.
9. Select the **Large Language Model** Name as **gpt-5**.
10. (optional) Select the **Model Version** from dropdown. By default, latest version will be considered.
11. Click the **Add** button
12. Click the **Add** prompt templates button.
13. In the Add Prompt Template dialog, enter the below prompt **Name**: `SYSTEM_PROMPT`<br>
The system prompt is used to set the overall context, behavior, or persona for the AI's responses. It provides the fundamental instruction set to guide the model's behaviour throughout an interaction.
14. Enter the below prompt **Description**: `Provide context to gpt-4o-mini model`
15. Enter the below **Prompt** text
```
You are provided with a sales dataset containing the following columns: Date, Product, Sales_Amount, and Units_Sold. Your task is to analyze this data and generate a professional summary report. The report should include the following:

1. **Key Performance Indicators (KPIs)**:
   - Total Sales Amount
   - Total Units Sold
   - Average Sales Amount per Day
   - Best-Selling Product
   - Highest Sales Day

2. **Summary of Key Findings**:
   - Identify any significant trends or patterns in the sales data.
   - Highlight any notable increases or decreases in sales.
   - Provide insights into the performance of different products.

**Conditions**:
- The output should be restricted to less than 500 words.
- The output should be in professional language.
```
16. Click the **Save** button.
17. Click the **OK** button in the confirmation dialog.
18. The added prompt should be visible in the Prompt Templates table.
19. Click the Add prompt templates button to add **User prompt**.
20. In the Add Prompt Template dialog, enter the below prompt **Name**: `USER_PROMPT`<br>
The second prompt will be an user prompt. User prompts are dynamic instructions or queries for an AI to perform a particular task.
21. Enter the below prompt **Description**:`Provide sales data for analysis`
22. Enter the below **Prompt** text<br>
```
Context: [EMBEDDING: Following contains sales data in INR for Annual Year 2023: {ISLM_SALES_DATA}]
Analyze the sales data and generate a concise and professional summary report
```
23. Click the **Save** button.
24. Click the **OK** button in the confirmation dialog.
25. The Prompt Templates table should display 2 prompts.
26. Click the **Save Draft** button.
27. Navigate back to Intelligent Scenario by clicking the **page back** button.
28. Click the **Publish** button.
29. Click the **Continue** button in Select Package Details dialog.
30. Click the **OK** button in configuration dialog.
31. Your Intelligent Scenario is published now. Search the Intelligent Scenario created by you by entering the **Intelligent Scenario name**.
Well done, you just created your first Side-by-side Intelligent Scenario.
