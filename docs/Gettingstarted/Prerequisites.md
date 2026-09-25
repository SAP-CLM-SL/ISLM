# Prerequisites

1. Add the S/4HANA system to SAP Logon

   **Windows**

   1. Click on **New** and select **Connection**.<br>
      ![Intelligent Scenarios](./images/Connection.png)
   2. Select **User Specified System** and click **Next**.<br>
      ![Intelligent Scenarios](./images/UserSpecifiedSystem.png)
   3. Enter the system details below (or refer to the cheat sheet if required) and click **Next**.<br>
      - **System ID (SID)**: S4H
      - **Application Server**: 44.219.212.100
      - **Instance Number**: 00
      - **Client**: 100
      - **Language**: EN<br>
      ![Intelligent Scenarios](./images/SystemDetails.png)
   4. Click **Next** and **Finish**.
   5. The system should now be visible in SAP Logon.<br>
      ![Intelligent Scenarios](./images/CAL.png)

   **Mac**

   1. Open SAP Logon (SAP GUI).
   2. Click **New Entry** (the "+" or "New Item" button in the toolbar).
   3. In the dialog, enter the description and select the **Advanced** tab.
   4. Enable **Expert Mode** and enter your IP address.<br>
      ![Intelligent Scenarios](./images/MacLogon.png)
   5. Click **Save**. The system should now appear in your SAP Logon list.

2. Attendee ID - ensures your ISLM Scenario name is unique across all participants.
3. Login credentials (if required):<br>
   - If prompted for a login ID and password, refer to the cheat_sheet.
   - The user ID and password are the same for both Fiori and Backend ABAP systems.
4. After logging into SAP Fiori Launchpad, access below applications
   - [Intelligent Scenarios](https://44.219.212.100:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#IntelligentScenario-register)
   - [Intelligent Scenario Management](https://44.219.212.100:44301/sap/bc/ui5_ui5/ui2/ushell/shells/abap/FioriLaunchpad.html?sap-client=100&sap-language=EN#IntelligentScenario-manage)
