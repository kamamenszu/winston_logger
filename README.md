<details>
<summary>Complaint</summary>

**Evidence page**

Path to execute tests: 
```
--specs=e2e/features/complaint/evidence/1-uploading-evidence.feature:<**Line**>
```

* **Scenario:** User should be able to upload an evidence || **Line:** `8`\
We check if user is able to upload an evidence to a complaint
* **Scenario:** User should be able to upload more then one evidence with various Evidence type || **Line:** `14`\
We check if user is able to upload more then one evidence. In this test we upload one evidence per one type.

**Message page**

Path to execute tests: 
```
--specs=e2e/features/complaint/messages/1-sending-message.feature:<Line>
```
* **Scenario:** Sending message with additional information || **Line:** `8`\
Passenger sends message to Administrator and attaches documents, then check if Administrator sees the same message title, body and attachment which Passenger sent to him.
</details>

<details>
<summary>Dashboard</summary>

Path to execute tests from this file: 
```
--specs=e2e/features/dashboard/1-log-in.feature:<Line>
```
* **Scenario:** Log in || **Line:** `8`\
This test check if each user role (all roles) can see only these column headers which he should see

Path to execute tests from this file: 
```
--specs=e2e/features/dashboard/2-filters.feature:<Line>
```
* **Scenario:** User with <role> should be able to see only these cases which he filtered by <condition> || **Line:** `7`
* **Scenario:** User with <role> should be able to searching for by <condition> || **Line:** `18`
* **Scenario:** User with <role> should be able to filtered cases by <condition> || **Line:** `29`\
 These tests describe how user with different role can search and filter cases. It check if user can see filtered/searched cases on the Dashboard
</details>

<details>
<summary>Miscellaneous</summary>

Path to execute tests from this file: 
```
--specs=e2e/features/miscellaneous/1-account-registration.feature:<Line>
```
* **Scenario:** Sign up validation || **Line:** `4`\
We check if the validation is working properly (e.g. checking validation info)
</details>

<details>
 <summary>Permissions</summary>
  
**Complaint**

Path to execute tests from this file: 
```
--specs=e2e/features/permissions/complaint/details-screen.feature:<Line>
```
* **Scenario:** As a <role> I should see the following headlines: <headlines> with sub-headings: <subHeadings> || **Line:** `8`\
 We check here if is it all OK with permissions to the Details screen. Which information see (and should see) each user with specific role. 
 </details>
 
<details>
 <summary>Submission-flow</summary>

Path to execute tests from this file: 
```
--specs=e2e/features/submission-flow/submission-flow.feature:<Line>
```
* **Scenario:** Customer should be able to create complaint || **Line:** `8`
* **Scenario:** User with <role> should be able to complete SF and have access to created complaint || **Line:** `14`\
 We check here if the Submission Flow is working properly for each role.
</details>

<details>
 <summary>Task-dashboard</summary>

Path to execute tests from this file: 
```
--specs=e2e/features/task-dashboard/1-task-dashboard.feature:<Line>
```
* **Scenario:** Assign complaint to SPTA || **Line:** `8`\
We check if the Administrator can assign cases to SPTA and then whether SPTA can see these assigned cases on his Tasks List. 
* **Scenario:** User should see a column with specific headers || **Line:** `14`\
This test check if each user role (administrator and SPTA) can see only these column headers which he should see
</details>

<details>
 <summary>Workflow</summary>
 
In these tests, we check whether the entire workflow works well. Is each case status is reachable and guidance are displayed correctly.\

Path to execute tests from this file: 
```
--specs=e2e/features/workflow/1-upload-evidence-status.feature:<Line>
```
* **Scenario:** The Next Action Box should present 'Upload Evidence' status || **Line:** `7`
* **Scenario:** The Next Action Box should present 'Appeal is being reviewed' status || **Line:** `13`

Path to execute tests from this file: 
```
--specs=e2e/features/workflow/2-acknowledge-appeal-status.feature:<Line>
```
* **Scenario:** The Next Action Box should present 'Has the passenger provided all information?' status || **Line:** `8`
* **Scenario:** The Next Action Box should present 'Assign Case' status after No more information is needed from passenger || **Line:** `14`

Path to execute tests from this file: 
```
--specs=e2e/features/workflow/3-receive-information-status.feature:<Line>
```
* **Scenario:** The Next Action Box should present 'Assign Case' status || **Line:** `8`

Path to execute tests from this file: 
```
--specs=e2e/features/workflow/4-assign-case-status.feature:<Line>
```
* **Scenario:** The Next Action Box should present 'Investigation' status || **Line:** `8`

Path to execute tests from this file: 
```
--specs=e2e/features/workflow/5-investigate-status.feature:<Line>
```
* **Scenario:** The Next Action Box should present 'Escalate to TOC' status || **Line:** `8`

Path to execute tests from this file: 
```
--specs=e2e/features/workflow/6-excalate-to-toc.feature:<Line>
```
* **Scenario:** The Next Action Box should present 'Awaiting TOC response' status || **Line:** `8`

Path to execute tests from this file: 
```
--specs=e2e/features/workflow/7-awaiting-resolution-status.feature:<Line>
```
* **Scenario:** The Next Action Box should present 'Awaiting resolution' status || **Line:** `8`

Path to execute tests from this file: 
```
--specs=e2e/features/workflow/8-log-outcome-status.feature:<Line>
```
* **Scenario:** Outcome message should be visible for user who create complaint. Status: complete || **Line:** `8`
</details>  

<br/> A feature file is made up of one or more Scenarios, and a Scenario is made up of the Given-When-Then steps. You can think of a Scenario as a test case and a Feature as a logical set of test cases.
