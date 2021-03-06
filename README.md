# Automation test for Transport Focus (TF) portal
This project refers to Transport Focus app. It's uses bdd tests which are readable and common understood by every team member.

## Table of contents
* [Installation](#installation)
* [Executing](#executing)
* [Setup](#setup)
* [Test cases](#test-cases)
* [Scripts](#scripts)
* [CircleCI](#circleci)
* [Technologies](#technologies)
* [Status](#status)
* [Contact](#contact)

## Installation
Make sure you have installed latest Node JS and Chrome browser. Once you clone repository, execute the following command to download all required dependencies
`npm install`
Then 
`npm start`

## Setup
Once the dependencies are installed, then you will be able to run the tests on staging. We use two variables to set up the API address and site address. Those two are:
* baseUrl `https://daas.resolvertest.com/`
* apiUrl `https://api-daas.resolvertest.com/`

If you would like to change addresses to your localhost use these two commands on console:
* `export $baseUrl="https://localhost:8080/"`
* `export $apiUrl="https://localhost:3000/"`

NOTICE: Please look at this movie, which demonstrate how to change base and API URLs directly from console:

![Localhost](/film.readme/localhost.gif)

## Executing
You can choose 3 different ways to run tests, depends on what you would like to run - all or only particular scenario. Open terminal in main folder and use following command:
* 1 - to start all tests:
```
npm run test
```
* 2 - to start tests only for workflow:
```
npm run basicWorkflow
```
* 3 - to start one test scenario:
``
node ./node_modules/protractor/bin/protractor ./protractor.sequential.conf.js  --capabilities.chromeOptions.prefs.download.default_directory=`pwd`/tmp --specs=e2e/features/dashboard/1-log-in.feature:8
``

NOTICE: If you would like to check different scenario, change `--specs=e2e/features/../..:..`.
First you should pick module you want to check, e.g. `dashboard` or `complaint` or `workflow`, then write name of feature file, e.g `1-account-registration.feature` or `5-investigate-status.feature` and write line number which Scenario is in file, e.g `14` or `8`. New path file to check different Scenario can be `--specs=e2e/features/miscellaneous/1-account-registration.feature:14`.

Look at this short film in GIF format, which demonstrate how to run only one scenario:

![Run_particular_Scenerio](/film.readme/1-log-in.feature:8.gif)

## Test cases
List of test cases in our project:

<details>
<summary>Complaint</summary>

**Evidence page**

Path to execute tests: 
```
--specs=e2e/features/complaint/evidence/1-uploading-evidence.feature:<Line>
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
 
In these tests, we check whether the entire workflow works well. Is each case status is reachable and guidance are displayed correctly.

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

## Scripts

This script allows you to create immediately 10 complaints at once. If you would like to use it, just type the command: `npm run createsf`. It creates them through the API.

## CircleCI
You can check very easily tests results in CircleCI. It allows you to see whether or not your automation tests are passing or failing, also it helps you to see what error occured during failling Scenario. Below you can find a GIF showing how to get to the daas testing repository.
![circleci](/film.readme/circleci.gif)

After passing to the cucumber automatically generated report, you can find which scenario passed...

![cucumber](/film.readme/cucumber.gif)

... and which failed:

![cucumber-failed](/film.readme/cucumber-failed.gif)

## Technologies
* cucumber - version 5.1.0
* typescript - version 2.7.2
* protractor - version 5.4.2
* chai - version 4.2.0

## Status
Project is: _in progress_.

## Contact
Created by @testarmy - feel free to contact us!
