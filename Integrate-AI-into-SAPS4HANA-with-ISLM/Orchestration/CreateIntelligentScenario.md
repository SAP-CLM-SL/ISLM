# Steps to Create Intelligent Scenarios<br>
1) Open the browser and navigate to the Fiori Launchpad by clicking [here](https://107.23.197.27:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html). We've already kept the system logged in. And under "Analytics" tab launch the "Intelligent Scenarios" application.
<img width="1887" height="887" alt="image" src="https://github.com/user-attachments/assets/04e5d9cb-5edd-4db4-ad1a-e415c73b04d9" />


2) Click the Create button and choose Side-by-Side.
<img width="1898" height="1026" alt="image" src="https://github.com/user-attachments/assets/ac244fc3-2b50-47c8-9102-777feed820ea" />


3) Then in the **Settings** tab:<br>
Select **Generative AI** as the **Scenario Type**.<br>
 <img width="1872" height="682" alt="image" src="https://github.com/user-attachments/assets/0a02d2f1-3940-4616-bb64-141c511cff01" />


4) Enter unique **Scenario name** in the below format, where ## is your attendee ID.<br>
```
Z_POL_DOC_SUMM_##
```
<img width="1887" height="825" alt="image" src="https://github.com/user-attachments/assets/f367d185-2618-4028-a391-801f5af56234" />


5) Enter the **description**<br>
```
Summarize Return Policy Document
```
<img width="1908" height="808" alt="image" src="https://github.com/user-attachments/assets/ac914c49-d445-4597-8d11-bd8acc609e82" />


6) Select **Stateless – Customer** as the Usage Type. <br>
This option provide the shared connectivity model allows a single connection between the ABAP system and the SAP Generative AI Hub to be configured once and reused across multiple AI use cases. This simplifies administration, improves governance, and reduces setup effort. Reuse connectivity is already set up and no action is required here for connectivity.
<img width="1898" height="860" alt="image" src="https://github.com/user-attachments/assets/8f90e45a-921f-4c74-a413-48cda52c8744" />



7) Add Generative AI Model to the Intelligent scenario<br>
Choose Add Model and maintain the required details:<br>
<img width="1887" height="812" alt="image" src="https://github.com/user-attachments/assets/e51cd336-e14f-4b72-8c92-bd8bedc90990" />


8) Enter a **model name** as **Z_POL_DOC_SUMMARIZE_MOD**<br>
   Enter the **description** as **Model with orchestration modules**<br>
<img width="1896" height="902" alt="image" src="https://github.com/user-attachments/assets/b6e54dc9-7b8e-472b-92de-957007970441" />


9) Select the appropriate **Executable ID** from the drop down. In this case, we will choose **azure-openai**<br>
<img width="1885" height="973" alt="image" src="https://github.com/user-attachments/assets/998ffd3a-ee39-4aa7-a700-dae3a183c66d" />


10) Select the corresponding **model** from the drop down. In this exercise, we will choose **gpt-5-mini**<br>
<img width="1733" height="976" alt="image" src="https://github.com/user-attachments/assets/9723847b-6d0c-4443-a2ec-8b75aaca49ea" />


11) (Optional) Choose a specific **model version** (latest is selected by default). In this case, we can keep as empty to have latest.<br>
<img width="1881" height="806" alt="image" src="https://github.com/user-attachments/assets/3608c543-4a06-45c6-95cb-6895a62ba39d" />


12) Choose **Add** to confirm<br>
<img width="1897" height="775" alt="image" src="https://github.com/user-attachments/assets/b13c7493-6fac-419b-b339-b6a1ba651c8d" />


13) Intelligent scenario with Orchestration service<br>

**Navigate to the Execution Flow Template**<br>
Upload  the orchestration Execution Flow JSON in this model to integrate the orchestration service. Refer to folder Orchestration config in your desktop. Open the config_json.txt file to see the orchestration configuration JSON. Select All & Copy.<br>
Use the Upload button to add the execution flow template or Paste the JSON into the dialog.<br>
<img width="1812" height="931" alt="image" src="https://github.com/user-attachments/assets/55a74148-b1f1-40c3-b8d7-d4aad2ad0d09" />


Once a valid JSON is uploaded, the modules will be displayed with their parameters and values in display mode.<br>
<img width="1820" height="926" alt="image" src="https://github.com/user-attachments/assets/769910a2-2a6e-460a-87d9-0bfd1f8421fa" />


14) In the **Grounding subsection**, add the required data repository type **vector**. This will support the grounding document addition.<br>
<img width="1908" height="1017" alt="image" src="https://github.com/user-attachments/assets/53ad01bf-13f7-4a28-b25c-770abe13bd21" />


To restrict your grounding module output during inference, maintain Search Configuration value. This can help to retrieve only relevant data instead of all the uploaded data.<br>
<img width="1900" height="1026" alt="image" src="https://github.com/user-attachments/assets/591098e7-d759-40ac-a146-78a4af2f7aec" />


The **Input Translation** module allows you to translate LLM text prompts and **grounding module** output into a target language. It may help improve LLM response when the configured model performs better with input in specific language, example English. In this use case, prompt texts are already English, so no need to maintain the Input translation configuration.<br>
Also, **Prompt Shield** is already true as per the JSON configuration file.<br>
<img width="1902" height="1012" alt="image" src="https://github.com/user-attachments/assets/b86f41e7-c35d-4389-af7d-4c35eaa0d8e2" />


15) The **Data Masking module** enables the anonymization or pseudonymization of data before it is sent to the LLM model for processing.

The **input filters** defined in the Execution Flow Template JSON are populated and displayed in the table.
<img width="1907" height="1020" alt="image" src="https://github.com/user-attachments/assets/83e19360-16c9-43b4-8918-313e1617d9f2" />


16) The **Output Filtering** module allows you to filter the harmful or hateful content generated by the LLM.<br>
The **Output Translation** module allows you to translate LLM response into a target language. It helps to display the LLM response in the language user logged, if the translation is supported.<br>
<img width="1912" height="1012" alt="image" src="https://github.com/user-attachments/assets/1b0bcc39-b12b-462f-85dc-0f2f72aab5c6" />


17) **Add Prompt & Grounding Template**<br>

**Add grounding template** <br>

Add a Grounding Template with name **GROUNDING_TEMPLATE** with description **Grounding query** and then add the below Grounding template text.<br>
```
{ISLM_GROUNDING_QUERY}
```
Select the **Display template information** as **Yes**. The grounding template can include dynamic parameters similar to the user prompt.<br>
The Grounding Template retrieves relevant information from the selected data repository and appends it to the user prompt. It supports dynamic parameters, which are provided at runtime (during inference).<br>
<img width="1917" height="1017" alt="image" src="https://github.com/user-attachments/assets/154c9827-25b6-4355-9bb4-23bc8b729c4a" />

<br></br>
<img width="1910" height="1007" alt="image" src="https://github.com/user-attachments/assets/5250ed2a-7211-4250-a983-77dbbdc28d1e" />


18) **Add prompt template for system prompt**<br>
<img width="1911" height="1023" alt="image" src="https://github.com/user-attachments/assets/ab35105e-92b9-444b-a5b7-79e6584b74da" />


Enter the prompt name **SYSTEM_PROMPT**. The system prompt is used to set the overall context, behavior, or persona for the AI's responses. It provides the fundamental instruction set to guide the model's behaviour throughout an interaction.<br>
Enter the description **Explain the role and responsibility for the LLM**<br>
Select the **Display template information** as **Yes**.<br>
Enter the below text as **Prompt text**<br>
```
 You are {ISLM_ROLE}. Your responsibility is to {ISLM_RESPONSIBILITY}.
```
Default parameter value of **ISLM_ROLE**:
```
An helpful assistant.
```
Default parameter value of **ISLM_RESPONSIBILITY**:
```
Assist the user with their queries.
```
<img width="1912" height="1021" alt="image" src="https://github.com/user-attachments/assets/7f43fa0d-e20a-41ac-bcd4-50af86d5cf7d" />


19) **Add prompt template for user prompt**<br>

Enter the prompt name **SUMMARIZE_RETURN_POLICY**<br>
Enter the description **Use LLM to summarize the return policy document to populate standard JSON**<br>
Select the **Display template information** as **Yes**.<br>
Enter the below text as **Prompt text**<br>
```
Generate a summary of return policy document provided below for the company {ISLM_COMPANY_NAME}.
 
### INSTRUCTIONS
- Populate the conditions of the return policy in the following JSON format
{
  "return_policy": {
    "overview": {
      "summary": "string",
      "free_returns": "boolean",
      "customer_friendly_notes": "string"
    },
    "return_window": {
      "days": "integer",
      "from_date": "string", // e.g., "from delivery date" or "from purchase date"
      "extensions": ["string"] // e.g., ["holidays", "defective items"]
    },
    "eligibility_criteria": {
      "conditions": ["string"], // e.g., ["unused", "original packaging", "with tags"]
      "proof_of_purchase": {
        "required": "boolean",
        "alternatives": ["string"] // e.g., ["order history", "email confirmation"]
      },
      "item_condition": "string" // e.g., "unworn, unwashed"
    },
    "non_returnable_items": {
      "categories": ["string"], // e.g., ["software", "undergarments", "perishables", "custom products", "final sale"]
      "reasons": ["string"]
    },
    "return_process": {
      "initiation_methods": ["string"], // e.g., ["online portal", "email support", "phone", "in-store"]
      "steps": ["string"],
      "return_authorization": {
        "required": "boolean",
        "form_url": "string",
        "label_provided": "boolean"
      },
      "shipping": {
        "who_pays": "string", // e.g., "customer", "merchant", "prepaid label"
        "instructions": "string",
        "address": "string",
        "preferred_carriers": ["string"]
      },
      "required_documents": ["string"] // e.g., ["receipt", "order number", "packing slip"]
    },
    "refund_options": {
      "types": ["string"], // e.g., ["full refund", "partial refund", "store credit", "exchange"]
      "default_method": "string",
      "payment_method": "string", // e.g., "original payment", "gift card"
      "processing_time": "string", // e.g., "3-5 business days"
      "fees": {
        "restocking_fee": {
          "amount": "number",
          "percentage": "number",
          "applies_to": ["string"]
        },
        "other_fees": ["string"]
      }
    },
    "shipping_costs": {
      "original_shipping": "boolean", // refundable?
      "return_shipping": "boolean" // refundable?
    },
    "special_cases": {
      "defective_damaged": {
        "extended_window": "boolean",
        "free_shipping": "boolean",
        "full_refund": "boolean"
      },
      "wrong_item": {
        "process": "string"
      },
      "holidays": "boolean",
      "other": ["string"]
    },
    "contact_info": {
      "support_email": "string",
      "phone": "string",
      "live_chat": "boolean",
      "return_center_url": "string"
    },
    "legal_notes": {
      "state_laws": ["string"],
      "warranties": "string"
    },
    "last_updated": "string" // for policy version tracking
  }
}
 
- Respond with only the JSON output
 
### RETURN POLICY DOCUMENT
{ISLM_GROUNDING_OUTPUT}
```

20) If you have configured grounding module, at least one User Prompt must be added with the following parameter: {ISLM_GROUNDING_OUTPUT}<br>
At runtime, this placeholder is automatically replaced with the content retrieved by the Grounding Template from the configured data repository.<br>
<img width="1907" height="1008" alt="image" src="https://github.com/user-attachments/assets/c1300e88-7b4e-46b8-a3e3-b947223b53f3" />
<br></br>
<img width="1910" height="1016" alt="image" src="https://github.com/user-attachments/assets/826e8bb2-30ea-4da8-83c5-ce410e382c18" />


21) **Save draft**<br>
<img width="1910" height="1017" alt="image" src="https://github.com/user-attachments/assets/bc4bdbec-1d4d-4d45-a407-1a8784dc9029" />


22) Navigate to Scenario documents section by pressing **Back**<br>
<img width="1871" height="870" alt="image" src="https://github.com/user-attachments/assets/373297f8-c320-4b7d-b3ed-8b7ba0c4be7d" />


23) **Upload grounding documents to an Intelligent Scenario**<br>
<img width="1903" height="1025" alt="image" src="https://github.com/user-attachments/assets/6067d664-dd96-40ec-851d-649f54ca84b8" />


24) Press Upload button<br>
<img width="1917" height="1021" alt="image" src="https://github.com/user-attachments/assets/18231304-8aa8-484f-937c-4c92372b8bfa" />


25) Select the below files from the Grounding files folder in your desktop<br>
<img width="1905" height="1016" alt="image" src="https://github.com/user-attachments/assets/8e976d66-d0d4-4d57-a2b1-439c726a9196" />


26) Enter the document names like below and choose **English** as language for all the files.<br>
<img width="1912" height="1012" alt="image" src="https://github.com/user-attachments/assets/5fac1a7d-8162-4e5a-a5ad-abd7ae234d60" />


27) Click Publish button<br>
Enter the package as local object $TMP
<img width="1908" height="1020" alt="image" src="https://github.com/user-attachments/assets/de937e07-dca9-4e0e-871c-827cb721015f" />


28) Press OK<br>
<img width="1912" height="1007" alt="image" src="https://github.com/user-attachments/assets/ca85ea77-a3f9-464f-99d3-99f1a0a21c5f" />

**Intelligent Scenario** is created successfully.

<br></br>
<p>
  <a href="Introduction.md">⬅️ Introduction</a>
  
  <a href="OperateIntelligentScenario.md">Operate Intelligent Scenario ➡️</a>
</p>
