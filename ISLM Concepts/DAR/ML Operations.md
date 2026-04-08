># Use Intelligent Scenario Management app to train, view model quality, deploy and activate the model

Once the Intelligent Scenario is published, the Intelligent Scenario Management app helps you to train, monitor the model quality, deploy, and activate the model for productive usage. In this section, you will use the Intelligent Scenario Management app to perform ML operations.

1. Open the Fiori Launchpad by clicking [here](https://18.214.3.29:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#Shell-home). Click the **Intelligent Scenario Management app**. 
<img width="1755" height="520" alt="image" src="https://github.com/user-attachments/assets/6f8ad51c-bb7d-4de3-9f2e-7ab4e35a6803" />

2. Find the scenario created by searching using the name (`Z_PRED_PLANETYPE_###`, where ### is your attendee id). Navigate to the details page by clicking the **>** icon. 
<img width="1908" height="534" alt="image" src="https://github.com/user-attachments/assets/920bc731-c49e-4be2-a20e-463a53dcbaf7" />

3. Select the Model and click the **Train** button to launch the train dialog. 
<img width="1876" height="591" alt="image" src="https://github.com/user-attachments/assets/1e3e4764-f319-4d3f-98e7-8e07efddf55d" />

4. In train dialog, select a **Version** from the remote machine learning provider by clicking the highlighted value help. 
<img width="1819" height="838" alt="image" src="https://github.com/user-attachments/assets/f056b8bf-8232-4f15-a240-c6822064f93d" />

5. Select the version **3.0** in the version field. 
<img width="1872" height="867" alt="image" src="https://github.com/user-attachments/assets/c529795e-2e46-416f-adf9-1b55b25b19ff" />

6. Review the information in the train dialog. Click the **Train** button. 
<img width="1522" height="745" alt="image" src="https://github.com/user-attachments/assets/9130d93c-7ea7-46ef-8288-91b0c27b403c" />

7. A new Training will be created in **Scheduled** status. 
<img width="1881" height="753" alt="image" src="https://github.com/user-attachments/assets/3e3cd06d-079e-4fad-8d2d-1aaf0d2582fd" />

8. Monitor the status of Training and check that the status changes to **Uploading Data**. 
<img width="1258" height="501" alt="image" src="https://github.com/user-attachments/assets/082938a7-8888-4814-8fec-9ed5c9dc50b5" />

9. After data upload is complete, the status will change to **Training**. 
<img width="1261" height="489" alt="image" src="https://github.com/user-attachments/assets/9af919f3-fc92-4dea-ab49-29d4581eea38" />

10. Wait for the status of the Training to change to Completed.
**Note**: that training can take around 5 minutes to complete. 
<img width="1254" height="460" alt="image" src="https://github.com/user-attachments/assets/4fa6e9be-60e9-4c4a-82c1-d875222dafcb" />

11. Click **>** icon to view the Training Details. 
<img width="1270" height="495" alt="image" src="https://github.com/user-attachments/assets/3dc0dbd8-8c42-4c55-967d-7f75dc073c5f" />

12. View the information in header section. Click the **Debrief** tab. 
<img width="1885" height="871" alt="image" src="https://github.com/user-attachments/assets/64b0417d-070d-4f12-808d-839bd202258e" />

13. View the **Overall** and individual **target** metrics in Debrief.
**Accuracy, F1Score, Precision** and **Recall** are classification metrics. The higher the value, better the model. 
<img width="1885" height="871" alt="image" src="https://github.com/user-attachments/assets/031aff92-172f-43cf-80ee-32a5cb485f18" />

14. Click the **Data Management** tab to view details of data packets which are uploaded to remote ML for training of the model. 
<img width="1902" height="543" alt="image" src="https://github.com/user-attachments/assets/b6e3b68d-9232-498d-8e32-b96c05f03a76" />

15. Click the back icon to navigate back to Trainings screen. 
<img width="1902" height="736" alt="image" src="https://github.com/user-attachments/assets/b00444e0-657b-46fc-a9bb-fcbe6fa8b456" />

16. Click the **Deploy** Button. 
<img width="1902" height="736" alt="image" src="https://github.com/user-attachments/assets/9ab56036-d075-4072-9f05-1d3ac2f37ec7" />

17. Verify the details in the **Deploy** dialog . Click **Deploy and Monitor** button. 
<img width="1719" height="826" alt="image" src="https://github.com/user-attachments/assets/0bf9331d-a79f-4f8e-919d-65404c065a15" />

18. A new Deployment is created in **Scheduled** status. 
<img width="1907" height="712" alt="image" src="https://github.com/user-attachments/assets/4cc80d02-90c1-4e02-abe3-2087c6576479" />

19. Monitor the status of Deployment and check the status changes to **Deployment Pending**. 
<img width="1285" height="565" alt="image" src="https://github.com/user-attachments/assets/5d496ab6-36b2-4ae8-9dc3-1f0a9651bccc" />

20. Monitor the status of Deployment and check the status changes to **Deployed**.
**Note**: that Deployments can take approximately 10 minutes to be Deployed. 
<img width="1255" height="535" alt="image" src="https://github.com/user-attachments/assets/e3260183-9339-4eae-9020-4c100963a3e4" />

21. To consume the resulting inference from this intelligent scenario the deployment must be activated. Select the Deployment and click the **Activate** button and choose **For All** option.
In the dialog Activate for All Users, choose **Activate For All**.
Validate that the Deployment has **Active for all** Indicator. 
<img width="1267" height="582" alt="image" src="https://github.com/user-attachments/assets/be40451b-3fbc-44a8-8c2f-ced5ea52b82e" />

**Well done, you just used Intelligent Scenario Management app to train, view model quality, deploy and activate the model.**
<br></br>
<p>
  <a href="Connect%20to%20SAP%20BTP.md">⬅️ Connect to SAP BTP</a>
  
  <a href="Inference.md">Inference ➡️</a>
</p>
