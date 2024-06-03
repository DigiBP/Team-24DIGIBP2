# Team-24DIGIBP2





# Team Members

1. Anjali Singh 
2. Hima Bindhu
3. Asfand Yar Arsalan



# Team Coach 

1. Charuta Pande
2. Andreas Martin


# Introduction:

This document describes the contribution to the process from Nish's Company As part of the course “Digitilaization of Businesss processes” At the university of applied Sciences and Arts North-western Switzerland.

# Description of the Use Case

In the digital age, paper-based systems prove to be cumbersome, error-prone, and time-intensive. For our project, we are inspired by Nish Technologies which was founded sometime in 2023 as people consulting company to provide services to its customers.. Nish essentially deals with payroll processing for its employees and timesheet and invoicing for its customers, acting as a middle person for both.it is currently on the brink of digital transformation as This company's current reliance on manual, paper-based processes for HR management makes it an ideal scenario for our digital solution.

One of the tasks that required attention was the generation of invoices created through the timesheets. The timesheets needed to be Created, Compiled, Checked and Reviewed which would then present information relevant to create the Invoices necessary so project expenses could be delivered to relevant project owners.

Our product SmartInvoice aims to streamline and automate the payroll processing, timesheet creation, and invoice generation. We will digitalize their existing processes through Camunda and Make which will not only simplify these processes but also enhances accuracy and accessibility.

There is no existing process model or workflow integration at Nish. Therefore, our Group created a best effort AS-IS BPMN process with the information they received from our Collegue. 




# Current Situation:

At Nish the existing payroll and timesheet management processes are predominantly manual.

•	Timesheet Submission: Employees fill out paper-based timesheets weekly, which are then manually checked by supervisors for errors or discrepancies before being handed over to the payroll department.

•	Payroll Processing: Payroll staff manually calculate hours, apply different rates (e.g., regular, overtime), and process payments. This process is prone to human error and often results in payment delays and employee dissatisfaction.

•	Invoice Generation: Invoices for contract labor or overtime work are manually prepared by accountants, a process that is time-consuming and often delayed, impacting cash flow and financial management



# Current AS-IS for Timesheet process and the Invoice generation process

The Timesheet Process is triggered by 2 events done by the Project worker.

1. Create timesheet, a worker manually generates the initial timesheet to be used in Excel based on the company specific template.

2. Send Timesheet, this is done by the system software in the form of email to the accounting department where the accountant becomes responsible for the second stage of events.

The Invoice generation process is now taken over by the accountant and is triggered by 7 events leading up to it.

1. Get mail from Inbox, the mail regarding timesheets by the project worker is received by the accountant.

2. Validation of Data, he must manually check that the input of all data and project information is correct.

3. If the project information is correct and project already exists, then we continue towards time entries. If the project information is correct but project does not exist, we transfer to another process to create project instead. However, if project exists but information is not correct then the process is stopped, and project worker is alerted.

4. Make time entries, based on the project information and input data received by the accountant, time entries are done to calculate exactly how much time is spent on the project.

5. Invoice creation, the invoice is now made through the final accounting based off time spent on the project.

6. Invoice download, the invoice generated is now downloaded by the accountant in print format 

7. Send invoice, the invoice is now sent to the respective company alerting them of their total bill/expenses incurred. 

<img width="468" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/3ce95111-bf21-4a6b-b950-a7f5c120d548">



# Description of the AS-IS Process elements and problem comments






| Row | Picture | Description | Comment |
| --- | ------- | ----------- | ------- |
| 1   | <img width="89" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/f4d47ce4-a1fa-4d94-9cfa-feaf790da3ff"> | Project worker creates a timesheet. | Initial step in the process. |
| 2   | <img width="89" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/cca99afd-aac1-43d2-a193-805a7201ec8c"> | Project worker sends the timesheet. | Hand-off to the accountant. |
| 3   | <img width="89" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/9394e14c-02bd-42e4-937c-aaaaf8547d03"> | Accountant retrieves the email containing the timesheet. | Accountant begins their workflow. |
| 4   | <img width="89" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/3823f0ca-1ea3-4e3d-ac3f-9ff69f1fc333"> | Accountant validates the data in the timesheet. | Ensures accuracy and completeness. |
| 5   | <img width="102" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/794054b6-4eb5-4ff9-b23f-382236b391d6"> | Accountant creates a project if it doesn’t already exist. | Conditional step based on project existence. |
| 6   | <img width="92" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/ce8f0efc-e380-4996-8691-404006c2359c"> | Accountant creates a project if it doesn’t already exist. | Conditional step based on project information. |
| 7   |  <img width="92" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/91cd13bd-0a2a-4fc1-b33b-e6bca97dcd6e"> | Accountant enters the time data into the system. | Continues only if the project exists. |
| 8   | <img width="92" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/00558128-ad8c-4c8a-99a0-c8690abf7f48"> | Accountant generates an invoice based on the time entry. | Key step for billing. |
| 9   | <img width="92" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/3bcebfa6-8ee7-48be-8253-0345f8fddaa0">| Accountant downloads the generated invoice. | Prepares for sending the invoice. |
| 10  | <img width="92" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/03bae9bf-24ef-479f-8e22-acd4bd6ed59b">| Accountant sends the invoice to the appropriate party. | Final step in the invoicing process. |





# AS-IS Business Process Problems

<img width="468" alt="image" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/9dd989b5-2673-4d57-825d-a30b6077bb62">


1. **Manual Data Validation**:The manual processes involved in timesheet and invoice management are fraught with inefficiencies and prone to errors. From the creation and dispatch of timesheets, which often lead to delays and loss of documents, to the accountant's time-consuming task of retrieving these timesheets from emails, each step lacks efficiency. Furthermore, the manual entry of timesheet data into systems and the subsequent creation of projects and invoices introduces a high potential for errors and inconsistencies. Finally, the process of manually downloading and sending invoices not only causes delays but also risks the correct delivery of these important documents, underscoring the need for more streamlined, automated solutions to enhance accuracy and reduce time wastage.


2.	**Dependence on Email for Workflow Triggers:** The process starts with "Get Mail from Inbox," indicating reliance on email to trigger activities such as validating data and creating invoices. This dependency on email can lead to delays and inefficiencies, especially if emails are missed or not processed promptly.

3.	**Sequential Process Flow:** The workflow seems very linear with a sequence of dependent steps. This can lead to bottlenecks, especially if any step takes longer than expected or if there are issues in the earlier stages of the process.

4.	**Lack of Integration:** The diagram suggests possible lack of integration between different systems (e.g., timesheet creation, invoice generation). Lack of integration can lead to redundant data entry, increased errors, and inefficiency.

5.	**Error Handling:** The process flow does not clearly define what happens when data is not validated (other than the workflow stopping at a "No" decision for "Project Exists"). There should be clear error handling and resolution processes to manage exceptions efficiently.

6.	**Feedback Loop:** There appears to be no feedback mechanism for the originators of the timesheets or the invoices (e.g., employees, project managers). Feedback loops are crucial for continuous improvement and error correction.

7.	**Scalability Issues:** The process as shown might not scale well with increasing numbers of employees or projects due to its manual and linear nature. As the company grows, the workload could become unmanageable without further automation or process optimization.






# To BE Process

 **PROCESS OVERVIEW:**




There are 2 main processes:


1. **Timesheet Management Process:** Deployed in Camunda as timesheet_management_to_be, this is the primary process that manages the entire lifecycle of employee timesheets. Each employee’s timesheet corresponds to one main process instance, capturing data from timesheet creation to final approval. At the begining of each month, this main process is initiated automatically, aggregating and validating all submitted timesheets. If discrepancies are found during the validation step, an email is triggered to the HR department to notify them. This ensures that only accurate timesheets proceed to the Invoice processing stage.

2. **Invoice Generation Process:** Deployed in Camunda as invoice_generation_to_be, this is the main process dedicated to the generation and management of invoices derived from approved timesheets activities. This process is initiated monthly, loading all relevant data to create and validate invoices. Each invoice creation corresponds to one main process instance, ensuring that each document is processed independently to maintain integrity and traceability.

These two sets of processes—timesheet management and invoice generation—are designed to enhance operational efficiency at Nish Technologies. By deploying these processes in Camunda, the company ensures that each critical task within timesheet and invoice management is handled systematically, reducing errors, improving turnaround times, and enhancing overall financial and operational control.






# Description of the TO-BE Process elements 




**TIMESHEET MANAGEMENT**


 **Employee**

| Row | Picture                                    | Description                                  | Comment                                     |
|-----|--------------------------------------------|----------------------------------------------|---------------------------------------------|
| 1   |  <img width="71" alt="Screenshot 2024-06-02 at 12 04 09 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/433f8440-9de8-4261-a10b-ffcfd5cfab3c"> | Employee initiates a timesheet request.      | This is the initial action by the employee to start the timesheet process. |
| 2   | <img width="71" alt="Screenshot 2024-06-02 at 12 04 18 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/97be5e80-5844-4eb6-b05f-f0e543641e5a"> | Time Sheet created by Template            | This step involves the system creating a timesheet. |


 **HR Department**
 
| Row | Picture | Description | Comment |
| --- | ------- | ----------- | ------- |
| 1   | <img width="77" alt="Screenshot 2024-06-02 at 12 15 39 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/43d68d10-13f1-48ad-8216-fbcea6f3549d">| Initiate loading of timesheets at the begining of each month for processing. | Critical for ensuring all timesheets are accounted for before processing begins.|
| 2   | <img width="77" alt="Screenshot 2024-06-02 at 12 15 46 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/9639c1ac-fa1c-43ad-8250-e28b39e88cd7"> | Retrieve customer information associated with the project. |Helps in linking timesheets to respective customers for billing|
| 3   | <img width="77" alt="Screenshot 2024-06-02 at 12 15 51 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/c336adec-c3f5-4bd4-8ab1-19a616a572fb"> |DMN to Determine whether the timesheet entries are billable. | Essential for financial processing and determining revenue from billable hours. |
| 4   | <img width="63" alt="Screenshot 2024-06-02 at 12 16 11 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/a1a85f97-bc9c-4365-a9bc-cde23fc20d14">| Decision point to check if the timesheets are billable. |  Decision-making step that influences downstream processing.  |
| 5   | <img width="63" alt="Screenshot 2024-06-02 at 12 16 23 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/2291792a-e91d-4180-aaaf-57e5c1b68b88">| Path followed if timesheets are billable. | Leads to further actions for billable entries, such as notifying accounts.|
| 6   | <img width="63" alt="Screenshot 2024-06-02 at 12 16 30 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/20d5dd01-755d-41e2-991e-54e9dc1b5a46">| Path followed if timesheets are not billable. |Routes the non-billable timesheets to appropriate handling procedures.  |
| 7   |<img width="77" alt="Screenshot 2024-06-02 at 12 16 45 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/e3b39d38-bd37-4540-a4c0-cd881e899320">| Notify the accounts department about the billable timesheets. | Ensures the accounts team is updated for invoicing and revenue recording. |
| 8   | <img width="77" alt="Screenshot 2024-06-02 at 12 17 30 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/df6fc6dc-ed0d-4f43-95b1-1fd045ebc4b9"> | Move timesheets to processed folder based on the outcome of billing checks. | Organizes timesheets into correct folders for archiving and error checking. |
| 9   | <img width="77" alt="Screenshot 2024-06-02 at 12 17 34 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/34128afe-8a31-41dd-be06-74a8f7529644">| Notify the HR department if timesheets are defective | Ensures HR is aware of the defective of timesheet which require further processing.|
| 10  | <img width="77" alt="Screenshot 2024-06-02 at 12 18 13 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/0c6a0081-68ba-4e28-b43d-e3575fd7f871">| Error Indicating timesheet validation failure. | ensures the validation failure is captured to further notify the HR department.|


**Project Manager**

| Row | Picture | Description | Comment |
| --- | ------- | ----------- | ------- |
| 1 | <img width="77" alt="Screenshot 2024-06-02 at 12 34 33 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/0092c3ff-f1da-4669-af3f-39c92d6e8756"> |  Checks if employees are allocated to a project | Ensures employees are appropriately allocated before timesheet approval. |
| 2 | <img width="77" alt="Screenshot 2024-06-02 at 12 34 41 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/e5582196-0691-4861-810a-da0068297e91">| Decision node to confirm if the employee is allocated to tasks. | Critical checkpoint to proceed with timesheet processing. |
| 3 | <img width="85" alt="Screenshot 2024-06-02 at 12 34 51 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/d4891224-fde6-442e-be6e-a472e4e50ea3">| **No**: Path taken if the employee has no current allocations. | Leads to system notification for allocation issue. |
| 4 | <img width="120" alt="Screenshot 2024-06-02 at 12 34 59 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/361031dc-e41f-4f48-b736-d8142d765234"> | **Yes**: Path taken if allocations are confirmed. | Proceeds to timesheet approval. |
| 5 | <img width="77" alt="Screenshot 2024-06-02 at 12 35 09 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/05976efe-25ba-453b-8e1d-db372d8928fc">|  Decision node to check if the timesheet meets approval criteria. | Gatekeeper for further timesheet processing steps. |
| 6 |<img width="77" alt="Screenshot 2024-06-02 at 12 57 51 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/afa4376c-5da2-4f09-884d-105a3f1e6170">|  Approves the timesheet after successful review. | Critical for proceeding to invoicing and record updates. |
| 7 | <img width="77" alt="Screenshot 2024-06-02 at 12 35 13 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/abedc5e4-3faa-421a-b3ea-27eeb5c1db53">|  Moves approved timesheets to the external processed folder. | Segregates processed timesheets for archival and auditing. |
| 8 | <img width="77" alt="Screenshot 2024-06-02 at 12 35 17 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/7e258198-ff05-4119-83b2-5b3537916aa2">|  Generates invoice records based on approved timesheets. | Integral for billing and financial documentation. |
| 9 | <img width="77" alt="Screenshot 2024-06-02 at 12 35 22 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/501e50fc-0b45-408e-9001-701b7f249d9d">| **C**: Represents the continuation of the process towards final invoicing and client notification. | Indicates ongoing process flow. |

**Line Manager**

| Row | Picture | Description | Comment |
| --- | ------- | ----------- | ------- |
| 1   | <img width="77" alt="Screenshot 2024-06-02 at 1 03 58 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/9d643d4e-6a49-41af-9ce5-29a19663bf9d">| Move to Processed-Timesheets(Internal) | Task to archive processed timesheets in an internal folder, ensuring organization and readiness for audits. |
| 2   | <img width="77" alt="Screenshot 2024-06-02 at 1 03 35 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/00466268-fa74-4d73-8d6f-5b1cc14a308e"> | Is Allocated to Internal Cost Center | Decision point to determine if expenses are allocated to an internal cost center, crucial for financial management. |
| 3   | <img width="77" alt="Screenshot 2024-06-02 at 1 03 28 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/704a89e9-cabb-4935-ac9a-327e13516d93">| Allocate to Internal Cost Center | Procedure to allocate expenses to the correct department's budget, aiding precise financial tracking. |
| 4   | <img width="77" alt="Screenshot 2024-06-02 at 1 03 23 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/b940aea6-6fec-4645-9c8b-759c666efadb">| Lightning Bolt Symbol (Task Trigger) | Indicates an automated process trigger, enhancing workflow efficiency and reducing manual effort. |
| 5   | <img width="77" alt="Screenshot 2024-06-02 at 1 03 11 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/53ae9f32-dfab-47b9-8790-c458c5ade782">| Is Hours within Limit | Ensures that the reported hours are within the permissible range, maintaining compliance and controlling overtime. |
| 6   | <img width="77" alt="Screenshot 2024-06-02 at 1 03 06 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/b09bbf6d-1896-453c-9164-39d8b24d1558">| Arrow with "B" | Directs to appropriate action if hours are outside the allowable range, potentially leading to further review or adjustment. |
| 7   | <img width="77" alt="Screenshot 2024-06-02 at 1 04 03 PM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/25a7fda2-a55f-47cf-900d-3cfdfbe65e0e">| Arrow with "C" | Represents the direction towards subsequent tasks, maintaining the workflow's continuity and efficiency. |





**Invoice Generation**

| Row | Picture | Description             | Comment                                              |
|-----|---------|-------------------------|------------------------------------------------------|
| 1   | <img width="93" alt="Screenshot 2024-06-02 at 11 23 54 AM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/941bb34d-8c35-4dc8-92c9-c726a0b6841f"> | Load Invoices | Invoices are loaded monthly for processing.         |
| 2   | <img width="93" alt="Screenshot 2024-06-02 at 11 24 04 AM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/94b440d5-7e3b-469f-ad23-976b1aacae82">| Validate Invoice | Each invoice is validated for accuracy and completeness. |
| 3   | <img width="93" alt="Screenshot 2024-06-02 at 11 24 11 AM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/cb056e31-e19a-409c-b99e-02a4205e92f5">| Review Invoice | Invoices undergo a detailed review to ensure they meet set criteria. |
| 4   | <img width="93" alt="Screenshot 2024-06-02 at 11 24 53 AM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/471e066f-cc46-4e8a-b441-aafcb9f893e8">| Move to Error Folder | Invoices that fail the review are moved to an error folder for correction. |
| 6   | <img width="93" alt="Screenshot 2024-06-02 at 11 24 34 AM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/64824990-2599-4b22-9499-b19bbfff3be9">| Send Invoice to Client | Approved invoices are sent to the client. |
| 7   | <img width="93" alt="Screenshot 2024-06-02 at 11 24 39 AM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/1b0789a1-4096-4da8-a3fe-b67f34c5d3ed">| Move to Processed Folder | Successfully processed invoices are stored in the processed folder. |
| 8   |  <img width="93" alt="Screenshot 2024-06-02 at 11 24 58 AM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/d2d3ddb8-8892-43fb-aa2d-c93e47e10dcd"> | Update Invoice Records | The records are updated to reflect the processed invoices. |
| 9   | <img width="93" alt="Screenshot 2024-06-02 at 11 25 02 AM" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/c58ab511-3a96-46d8-b9f8-3543e16093d2">| Notify Accounts Manager | The accounts manager is notified upon completion or issues. |

















# Process 1: Timesheet Management Process



Camunda Model for Timesheet:
<img width="917" alt="TO-BE TimeSheet creation" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/cb2bd969-a522-4b93-9a62-34e326805e86">









**Step 1:** Create Timesheet Request



<img width="850" alt="Create Timesheet Form" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/1bb3a31f-5243-4ec3-bb31-4aee2cb61552">


Form Submission: Employees start by filling out a digital form to create a timesheet request. This form captures essential details such as the employee name, title, and project ID. The form, managed through Camunda's user task interface, ensures that all necessary data is collected efficiently and accurately.










**Step 2:** Automate Timesheet Creation



<img width="1265" alt="Create Timesheet Make" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/135dab83-b0a6-4568-8fb8-3ea2550e2e20">



Triggering Custom Webhook: Once the form is submitted, a custom webhook is triggered.
Google Sheets Integration: The webhook initiates a process where a new timesheet is created from a predefined template in Google Sheets. This automation ensures that the timesheet format is consistent and standardized for all entries.
Webhook Response: After the spreadsheet is created, a confirmation is sent back through another webhook, signaling the successful creation of the timesheet.







**Step 3:** Load and Process Timesheets



<img width="1312" alt="Load Timesheet Make" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/8b02c6cd-1fae-4ac2-9b91-85dee7b9f04a">


Monthly Batch Processing: At the end of each month, another automated process is initiated via Make to load all timesheets for the current month. This involves searching for relevant files in Google Drive, followed by compiling and organizing the data using Google Sheets and other tools to aggregate and format the data appropriately.







**Step 4:** Determine Project Details and Billability


<img width="1312" alt="Get Project for timesheet" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/fdcd8223-6cde-4681-a995-879156c9c62e">
<img width="732" alt="DMN Overview" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/bbb6f18b-b8a1-47c6-ba2c-d701242978de">
<img width="882" alt="DMN Table 1" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/d7ebbf8f-1fd6-445d-a464-c71ddb6305f4">
<img width="1093" alt="DMN Table 2" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/1474b244-c3ec-4da1-9fc6-d6ee9c819167">



Fetching Project Details: Using a combination of Google Sheets and custom logic (e.g., webhooks and scripting), the process fetches detailed project information related to each timesheet. This includes determining the project's current status and its customer details.

Decision Making Using DMN: Decision Model and Notation (DMN) tables are utilized to ascertain whether the project is billable based on its status and other characteristics. This helps in categorizing the timesheets into billable and non-billable.







**Step 5:** Allocate to Employees


<img width="1312" alt="Employee allocation make" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/a44f25a3-9710-4d2f-ad9d-f5313bd48c26">


Employee Allocation: A specific process in Make checks the allocation of each employee to projects. This step ensures that timesheets are accurately associated with the right employee and project, which is crucial for accurate payroll processing.








**Step 6:** Finalize and Move Timesheets


<img width="1312" alt="Move to external folder timesheet Make" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/8d13891d-4243-4b69-bd81-f6717fb9b4e5">
<img width="1424" alt="External folder for processed timesheet" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/69d81536-a197-40f9-b295-2b821c3116e1">



Move Processed Timesheets: After all validations and allocations are confirmed, the finalized timesheets are moved to an "external" folder in Google Drive dedicated to processed timesheets. This step is crucial for maintaining organized records and ensuring that processed data is stored securely and separately from ongoing entries.







**Step 7:** Integration and Accessibility

<img width="467" alt="Generated taks form" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/bc30b734-523a-4741-9d58-765dfffd6b59">
<img width="485" alt="Google sheet form" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/687eb7ca-4032-4ca6-842d-c38fb1e0c5e4">



Accessibility: All processed timesheets in the Google Drive folder are now easily accessible for further review, audit, or archival purposes. This final step ensures that the data is not only processed correctly but also stored in a way that supports easy retrieval and compliance with data management practices.



This TO-BE process for Timesheet Management streamlines the entire cycle from creation to processing, leveraging automation tools like Make and decision-making frameworks like DMN in Camunda. It ensures efficiency, accuracy, and compliance in managing employee timesheets at Nish Technologies, transforming the manual and error-prone tasks into a smooth, automated workflow.









# Process 2:  Invoice Generation Process

Camunda Model for Invoice Generation

<img width="774" alt="To-BE Invoice Generation" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/dbd3975a-8903-4dac-9d6f-728875c22ca2">




**Step 1:** Generate Invoice Record from Template


Description: The process initiates with a custom webhook that triggers the creation of an invoice record. The invoice is generated from a predefined template in Google Sheets to ensure uniformity and accuracy.



<img width="1339" alt="Generate invoice Make" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/c4bad08c-a287-4317-ae01-3f48e674db25">





**Step 2:** Store Invoice Records



<img width="1433" alt="Invoice Template Records google" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/f2288d3b-7516-4229-966e-3c0b4ac6bf31">



Description: The invoice generation process begins with a custom webhook that triggers the automated creation of an invoice from a predefined template in Google Sheets. This approach ensures that every invoice adheres to the company's standards for uniformity and accuracy, laying the groundwork for reliable financial documentation.

**Step 3:** Notify Accounts Department



<img width="1351" alt="Notify accounts department make" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/fe4960c6-ef52-4cab-a0bb-fe85146911ca">




Description: Following the generation of the invoice, the accounts department is automatically notified. This notification process involves downloading the invoice from Google Drive, sending an email to the accounts department, and confirming the notification with a webhook response, ensuring that the accounts team can immediately start their review and processing tasks.






**Step 4:** Move Processed Timesheets to Appropriate Folders



<img width="1325" alt="move processed timesheet error" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/d9409edf-ce29-4028-b491-491f1a1d06f8">
<img width="1325" alt="move processed timesheet to internal folder" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/32c1648d-a71a-4c0a-8508-185def77eb83">





Description: Based on the outcome of the invoice validation—successful or erroneous—the corresponding timesheets are moved to either an internal folder for successful transactions or an error folder for those needing further review. This automatic sorting helps in segregating and prioritizing tasks for rectification or further processing.







**Step 5:** Load and Review Invoices



<img width="1325" alt="Load Invoices" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/2d3422cf-ebf3-4a07-b81f-81d8ca7f4896">




Description: Invoices are periodically loaded and reviewed to ensure they meet all required standards and specifications. This regular audit and quality check help in maintaining compliance and accuracy in the financial documentation, safeguarding against potential financial discrepancies or errors.










**Step 7:** Final Processing and Record Updates



<img width="1325" alt="Move to processed folder(success)" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/0bfd0090-d502-49af-8f6b-d1521597ea72">
<img width="1325" alt="Update Invoice Records" src="https://github.com/DigiBP/Team-24DIGIBP2/assets/161338513/7b280f86-0f17-49df-bd02-f3a2bcaf1f7b">




Description: Upon successful processing, invoices are moved to a 'processed' folder, indicating the completion of their lifecycle. Simultaneously, invoice records in Google Sheets are updated to reflect their current status. This final step ensures that all invoice data is up-to-date and accurately reflected in financial reports and audits






















This TO-BE process for Invoice Generation optimizes the entire invoicing cycle, utilizing automation tools such as Make to enhance precision and streamline workflows.This transformation ensures greater efficiency, compliance, and overall satisfaction in invoice management at Nish Technologies, representing a significant leap forward from the previous, more manual processes.





# Conclusion

The enhanced TO-BE processes for Invoice Generation and Timesheet Management at Nish Technologies exemplify significant advancements in financial and workforce management, leveraging the automation capabilities of Make and the robust modeling features of Camunda. These technologies ensure that both invoices and timesheets are processed with high accuracy and efficiency, minimizing the potential for human error and maximizing operational productivity. Make facilitates the automation of complex workflows, enabling tasks to be carried out swiftly and seamlessly. Simultaneously, Camunda's BPMN modeling provides a clear, visual framework for managing and optimizing these business processes, enhancing transparency and accountability across departments. This integration not only streamlines data handling and processing but also frees up valuable resources, allowing staff to focus on strategic growth initiatives. Overall, these improvements lead to better regulatory compliance, improved stakeholder satisfaction, and a more agile response to market demands.


# Suggestions

To further refine and enhance the processes of invoice generation and timesheet management, Nish Technologies could consider several improvements. Integration with ERP systems would offer a more unified view of operational and financial data, enhancing real-time decision-making and financial planning. The implementation of machine learning algorithms could preemptively identify anomalies, significantly improving the accuracy and efficiency of processing. Strengthening security protocols around sensitive data through advanced encryption and multi-factor authentication will safeguard against breaches and unauthorized access. Establishing continuous feedback loops with employees and clients will enable the company to promptly address any issues and adapt processes to better meet stakeholder needs. Furthermore, ongoing training programs will ensure that employees remain knowledgeable about the latest technologies and process updates, maximizing their ability to effectively leverage these tools. By embracing these suggestions, Nish Technologies will not only optimize current operations but also maintain its competitive edge in a dynamically evolving business landscape.



