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


