# Team-24DIGIBP2





# Team Members

1. Anjali Singh 
2. Hima Bindhu
3. Asfand Yar Arsalan



# Team Coach 

1. Charuta Pande
2. Andreas Martin


# Introduction:

This document describes the contribution to the process from Jan’s Company As part of the course “Digitilaization of Busienss processes” At the university of applied Sciences and Arts North-western Switzerland.

# Description of the Use Case

In the digital age, paper-based systems prove to be cumbersome, error-prone, and time-intensive. For our project, we are inspired by Nish Technologies which was founded sometime in 2023 as internet solutions company to provide its customers help with Payroll processing. Nish essentially functions as a solution provider for HR-related challenges, offering digital tools and platforms designed to improve the efficiency and accuracy of tasks traditionally handled by human resources departments.it is on currently on the brink of digital transformation as This company's current reliance on manual, paper-based processes for HR management makes it an ideal scenario for our digital solution.

One of the tasks that required attention was the generation of invoices created through the timesheets. The timesheets needed to be Created, Compiled, Checked and Reviewed which would then present information relevant to create the Invoices necessary so project expenses could be delivered to relevant project owners.

Our project aims to streamline and automate the payroll processing, timesheet creation, and invoice generation. We will digitalize their existing processes through Camunda and Make which will not only simplify these processes but also enhances accuracy and accessibility.

There is no existing process model or workflow integration at Nish. Therefore, the Group created a best effort AS-IS BPMN process with the information they received from Jan. 
As-IS Process Description



# Current Situation:

At Nish the existing payroll and timesheet management processes are predominantly manual.

•	Timesheet Submission: Employees fill out paper-based timesheets weekly, which are then manually checked by supervisors for errors or discrepancies before being handed over to the payroll department.

•	Payroll Processing: Payroll staff manually calculate hours, apply different rates (e.g., regular, overtime), and process payments. This process is prone to human error and often results in payment delays and employee dissatisfaction.

•	Invoice Generation: Invoices for contract labor or overtime work are manually prepared by accountants, a process that is time-consuming and often delayed, impacting cash flow and financial management



# The following process is combination of both the Timesheet process and the Invoice generation process

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

8.	**Audit and Compliance:** The process does not explicitly mention any steps for audit and compliance checks, which are essential for financial transactions like invoicing and payroll.


9.	**Data Silos:** Data related to timesheets, projects, and invoices may be stored in disparate systems, leading to data silos and inefficiencies.





# To BE Process

 **PROCESS OVERVIEW:**




There are 2 main processes:


1. **Timesheet Management Process:** Deployed in Camunda as timesheet_management_to_be, this is the primary process that manages the entire lifecycle of employee timesheets. Each employee’s timesheet corresponds to one main process instance, capturing data from timesheet creation to final approval. At the end of each month, this main process is initiated automatically, aggregating and validating all submitted timesheets. If discrepancies are found during the validation step, a corrective action process is triggered for the employee to revise and resubmit their timesheet. This ensures that only accurate timesheets proceed to the payroll processing stage.

2. **Invoice Generation Process:** Deployed in Camunda as invoice_generation_to_be, this is the main process dedicated to the generation and management of invoices derived from approved timesheets and other billable activities. This process is initiated monthly or as needed, loading all relevant data to create and validate invoices. Each invoice creation corresponds to one main process instance, ensuring that each document is processed independently to maintain integrity and traceability.

These two sets of processes—timesheet management and invoice generation—are designed to enhance operational efficiency at Nish Technologies. By deploying these processes in Camunda, the company ensures that each critical task within timesheet and invoice management is handled systematically, reducing errors, improving turnaround times, and enhancing overall financial and operational control.


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


(INCLUDE IMAGES OF GOOGLE MAKE DETAILS)

Accessibility: All processed timesheets in the Google Drive folder are now easily accessible for further review, audit, or archival purposes. This final step ensures that the data is not only processed correctly but also stored in a way that supports easy retrieval and compliance with data management practices.



This TO-BE process for Timesheet Management streamlines the entire cycle from creation to processing, leveraging automation tools like Make and decision-making frameworks like DMN in Camunda. It ensures efficiency, accuracy, and compliance in managing employee timesheets at Nish Technologies, transforming the manual and error-prone tasks into a smooth, automated workflow.











