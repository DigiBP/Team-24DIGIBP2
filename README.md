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

