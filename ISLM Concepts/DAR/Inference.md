># View the inference result returned by the model in an ABAP report

In this step, you will use the ABAP GUI to view the inference result from the trained model.

1. Open transaction **/nSE38** in **S4H** system in the SAP GUI. 
<img width="1160" height="195" alt="image" src="https://github.com/user-attachments/assets/d15893fc-9f36-423f-87fd-b0d993b178cf" />

2. Enter the Report Name as `ZR_ISLM_TEST_OPERATION_API` and Click the **Execute** button. 
<img width="809" height="454" alt="image" src="https://github.com/user-attachments/assets/e5ad0639-6db3-4048-940b-e6a8caca7e2b" />

3. Choose the option **Side-By-Side**. In the API Definition, select **TRIGGER_ONLINE_INFERENCE** from drop down. 
<img width="1115" height="521" alt="image" src="https://github.com/user-attachments/assets/4bdbb3d7-0a8c-4ae2-a6be-015f0f4b1f55" />

4. Enter the prediction class associated with your Intelligent Scenario (`ZCL_PLANTYPE_###`, where ### is your attendee id).
Click the **Execute** button. 
<img width="1089" height="510" alt="image" src="https://github.com/user-attachments/assets/c71080da-fb4f-4f4e-86e9-4cefc5d8571c" />

5. Your trained model is now ready to predict the target **PLANETYPE**. To predict this target, inputs to model has to be provided.
Copy the below text which contains the Inference Request with inputs in JSON format.
Inference Request contains the features and its value which is input for the trained model.
**topN**- Parameter which defines how many options will be predicted.
Inputs would be **FLDATE, PRICE, SEATSMAX, SEATSOCC, SEATSMAXB, SEATSMAXF, SEATSOCCB, SEATSOCCF, PAYMENTSUM, CURRENCY**.

```
{
  "topN": 2,
  "objects": [
    {
      "objectId": "optional-identifier-5",
      "features": [
        {
          "name": "FLDATE",
          "value": ""
        },
        {
          "name": "PRICE",
          "value": "422.94"
        },
        {
          "name": "SEATSMAX",
          "value": "385"
        },
        {
          "name": "SEATSOCC",
          "value": "374"
        },
        {
          "name": "SEATSMAXB",
          "value": "31"
        },
        {
          "name": "SEATSMAXF",
          "value": "21"
        },
        {
          "name": "SEATSOCCB",
          "value": "29"
        },
        {
          "name": "SEATSOCCF",
          "value": "21"
        },
        {
          "name": "PAYMENTSUM",
          "value": ""
        },
        {
          "name": "CURRENCY",
          "value": ""
        }
      ]
    }
  ]
}
```

6. Paste the copied text in the **text editor**. Click on **tick** icon. 
<img width="1719" height="961" alt="image" src="https://github.com/user-attachments/assets/77d70c40-f354-4717-a0f6-85292678db9e" />

7. View the response from the trained model.
In the response, you find the values that the model predicted. This includes the value that is predicted and the probability.
The probability describes how certain the model is about its prediction. **If the probability is close to 1, the model is very certain**. Model predicts the PLANETYPE with two possible values(as defined in Inference request **"topN": 2**).
For predicted value of **A319-100**, the probability will be **1.0**.
For predicted value of **747-400**, the probability will be **0.0**. 
<img width="809" height="490" alt="image" src="https://github.com/user-attachments/assets/c93bd6fe-42e1-4f2f-976e-3bac9376f8a4" />

**Note**: The predicted values and the probabilities depend heavily on the inputs, the training data as well as the training metrics

Well done, you just Viewed the inference result returned by the model in an ABAP report.

🎉 Congratulations! You have successfully completed the Exercise!🎉

<br></br>
<p>
  <a href="ML%20Operations.md">⬅️ ML Operations</a>
  
  <a href="../Community/Blogs.md">Blogs ➡️</a>
</p>
