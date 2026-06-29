# Steps to Create Intelligent Scenarios<br>
1. Open the browser and navigate to the Fiori Launchpad by clicking [here](https://44.219.212.100:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html#Shell-home) and under "Analytics" tab launch the "Intelligent Scenarios" application.
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/017.jpg)

2. Click the **Create** button and choose **Side-by-Side**.
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/02.png)

3. Next, go to the **Settings** tab and select **Generative AI** as the Scenario Type.<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/02.jpg)

4. Enter unique **Scenario name** in the below format, where ## is your attendee ID.<br>
```
Z_POL_DOC_SUMM_##
```
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/03.jpg)

5. Enter the **description**<br>
```
Summarize Return Policy Document
```
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/04.jpg)

6. Select **Stateless – Customer** as the Usage Type. <br>
This option provide the shared connectivity model allows a single connection between the ABAP system and the SAP Generative AI Hub to be configured once and reused across multiple AI use cases. This simplifies administration, improves governance, and reduces setup effort. Reuse connectivity is already set up and no action is required here for connectivity.
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/05.jpg)


7. Add a Generative AI model to the Intelligent Scenario by selecting **Add Model** and providing the required details. <br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/06.jpg)

8. Enter the below details: <br>
- **Model name** as `Z_POL_DOC_SUMMARIZE_MOD`<br>
- **Description** as `Model with orchestration modules`<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/07.jpg)

9. Select the appropriate **Executable ID** from the drop down. In this case, we will choose **azure-openai**<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/08.jpg)

10. Select the corresponding **Model** from the drop down. In this exercise, we will choose **gpt-5-mini**<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/09.jpg)

11. Optionally, choose a specific **Model Version** (latest is selected by default). In this case, we can keep as empty to have latest.<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/010.jpg)

12. Choose **Add** to confirm<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/011.jpg)

13. Intelligent scenario with Orchestration service:
- Navigate to the **Execution Flow Template**<br>
- Upload the Execution Flow Template
   - Click the **Upload** button.
   - Either select all and copy the JSON from [config file](https://github.com/SAP-CLM-SL/ISLM/raw/main/docs/Integrate-AI-into-SAPS4HANA-with-ISLM/OrchestrationConfigFiles/Orchestration%20config.zip), or paste the below JSON directly into the dialog.
```
{
  "module_configurations": {
    "grounding_module_config": {
      "type": "document_grounding_service",
      "config": {
        "filters": [
          {
            "id": "filter1",
            "data_repositories": [
              "2a35766b-e72e-4ef8-9223-5995c839b1cd"
            ],
            "search_config": {
              "max_document_count": 0
            },
            "data_repository_type": "vector"
          }
        ],
        "input_params": [
          "grounding_input_variable_1"
        ],
        "output_param": "grounding_output_variable"
      }
    },
    "llm_module_config": {
      "model_name": "gpt-5-mini",
      "model_params": {},
      "model_version": {}
    },
    "templating_module_config": {
      "template_ref": {}
    },
    "filtering_module_config": {
      "input": {
        "filters": [
          {
            "type": "azure_content_safety",
            "config": {
              "Hate": 0,
              "SelfHarm": 0,
              "Sexual": 0,
              "Violence": 0
            }
          },
          {
            "type": "llama_guard_3_8b",
            "config": {
              "child_exploitation": true,
              "code_interpreter_abuse": true,
              "defamation": true,
              "elections": true,
              "hate": true,
              "indiscriminate_weapons": true,
              "intellectual_property": true,
              "non_violent_crimes": true,
              "privacy": true,
              "self_harm": true,
              "sex_crimes": true,
              "sexual_content": true,
              "specialized_advice": true,
              "violent_crimes": true
            }
          }
        ]
      },
      "output": {
        "filters": [
          {
            "type": "azure_content_safety",
            "config": {
              "Hate": 0,
              "SelfHarm": 2,
              "Sexual": 4,
              "Violence": 6
            }
          },
          {
            "type": "llama_guard_3_8b",
            "config": {
              "child_exploitation": true,
              "code_interpreter_abuse": true,
              "defamation": true,
              "elections": true,
              "hate": true,
              "indiscriminate_weapons": true,
              "intellectual_property": true,
              "non_violent_crimes": true,
              "privacy": true,
              "self_harm": true,
              "sex_crimes": true,
              "sexual_content": true,
              "specialized_advice": true,
              "violent_crimes": true
            }
          }
        ]
      }
    },
    "masking_module_config": {
      "masking_providers": [
        {
          "type": "sap_data_privacy_integration",
          "method": "anonymization",
          "entities": [
            {
              "type": "profile-email"
            },
            {
              "type": "profile-gender"
            },
            {
              "type": "profile-pronouns-gender"
            },
            {
              "type": "profile-location"
            },
            {
              "type": "profile-person"
            },
            {
              "type": "profile-url"
            }
          ],
          "mask_grounding_input": {
            "enabled": true
          },
          "allowlist": [
            "ANALYTICS",
            "SPECIALIST"
          ]
        }
      ]
    },
    "input_translation_module_config": {},
    "output_translation_module_config": {}
  }
}
```
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/4.jpg) <br>
- Once a valid JSON is uploaded, the modules will be displayed with their parameters and values in display mode.<br>

14. In the **Grounding subsection**, add the required data repository type **Vector**. This will support the grounding document addition. Click [here](https://github.com/SAP-CLM-SL/ISLM/raw/main/docs/Integrate-AI-into-SAPS4HANA-with-ISLM/GroundingFiles/Grounding%20files.zip) to download the grounding files. <br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/019.jpg) <br>
To restrict your grounding module output during inference, maintain Search Configuration value. This can help to retrieve only relevant data instead of all the uploaded data.<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/021.jpg)<br>

16. The **Input Translation** module allows you to translate LLM text prompts and **grounding module** output into a target language. It may help improve LLM response when the configured model performs better with input in specific language, example English. In this use case, prompt texts are already English, so no need to maintain the Input translation configuration.<br>
Also, **Prompt Shield** is already true as per the JSON configuration file.<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/6.jpg)

17. The **Data Masking module** enables the anonymization or pseudonymization of data before it is sent to the LLM model for processing. <br>
The **Input filters** defined in the Execution Flow Template JSON are populated and displayed in the table.
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/7.jpg)

18. The **Output Filtering** module allows you to filter the harmful or hateful content generated by the LLM.<br>
The **Output Translation** module allows you to translate LLM response into a target language. It helps to display the LLM response in the language user logged, if the translation is supported.<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/014.jpg)

19. Add **Prompt** & **Grounding Template**<br>
- Add a Grounding Template with name **GROUNDING_TEMPLATE** with description **Grounding query** and then add the below Grounding template text.<br>
``` 
{ISLM_GROUNDING_QUERY}
``` 
- Select the **Display template information** as **Yes**. The grounding template can include dynamic parameters similar to the user prompt.<br>
- The Grounding Template retrieves relevant information from the selected data repository and appends it to the user prompt. It supports dynamic parameters, which are provided at runtime (during inference).<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/9.jpg)
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/10.jpg)

19. Add **Prompt template** for **System prompt**<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/11.jpg) <br>
- Enter the prompt name **SYSTEM_PROMPT**. The system prompt is used to set the overall context, behavior, or persona for the AI's responses. It provides the fundamental instruction set to guide the model's behaviour throughout an interaction.<br>
- Enter the description **Explain the role and responsibility for the LLM**<br>
- Select the **Display template information** as **Yes**.<br>
Enter the below text as **Prompt text**: `You are {ISLM_ROLE}. Your responsibility is to {ISLM_RESPONSIBILITY}.` 
- Default parameter value of **ISLM_ROLE**: `An helpful assistant.` 
- Default parameter value of **ISLM_RESPONSIBILITY**: `Assist the user with their queries.`
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/12.jpg)

20. Add **Prompt template** for **User prompt**<br>
- Enter the prompt name: `SUMMARIZE_RETURN_POLICY`
- Enter the description `Use LLM to summarize the return policy document to populate standard JSON`
- Select the **Display template information** as **Yes**.
- Enter the below text as **Prompt text**<br>
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

21. If you have configured grounding module, at least one User Prompt must be added with the following parameter: {ISLM_GROUNDING_OUTPUT}<br>
At runtime, this placeholder is automatically replaced with the content retrieved by the Grounding Template from the configured data repository.<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/13.jpg)
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/14.jpg)

22. Save **Draft**<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/15.jpg)

23. Navigate to Scenario documents section by pressing **Back**<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/022.jpg)

24. Upload grounding documents to an Intelligent Scenario<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/16.jpg)

25. Press **Upload** button<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/17.jpg)

26. Select the below files from the Grounding files folder in your desktop<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/18.jpg)

27. Enter the document names like below and choose **English** as language for all the files.<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/015.jpg)

28. Click **Publish** button and enter the package as **local object $TMP**
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/020.jpg)

29. Press **OK**<br>
![Intelligent Scenarios](Integrate-AI-into-SAPS4HANA-with-ISLM/../IntelligentScenario/21.jpg)

**Intelligent Scenario** is created successfully.
