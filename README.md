# Cucumber test for Transport Focus (TF) portal
This project refers to Transport Focus app. It's uses bdd tests which are readable and common understood by every team member.

## Table of contents
* [Installation](#installation)
* [Executing](#executing)
* [Setup](#setup)
* [Features](#features)
* [Scripts](#scripts)
* [CircleCI](#circleCI)
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

![localhost](/film.readme/localhost.gif)

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
* 3 - to start one test scenerio:
``
node ./node_modules/protractor/bin/protractor ./protractor.sequential.conf.js  --capabilities.chromeOptions.prefs.download.default_directory=`pwd`/tmp --specs=e2e/features/dashboard/1-log-in.feature:8
``

NOTICE: If you would like to check diffrent scenerio, change `--specs=e2e/features/../..:..`.
First you should pick module you want to check, e.g. `dashboard` or `complaint` or `workflow`, then write name of feature file, e.g `1-account-registration.feature` or `5-investigate-status.feature` and write line number which Scenerio is in file, e.g `14` or `8`. New path file to check diffrent Scenerio can be `--specs=e2e/features/miscellaneous/1-account-registration.feature:14`.

Look at this short film in gif format, which demonstare how to run only one scenerio:

![Run_particular_Scenerio](/film.readme/1-log-in.feature:8.gif)

## Features
List of features in our project:

### Complaint
**Evidence page**
##These tests describe how Passenger uploads evidence (e.g pdf, image) and checks if He see it on Evidence Page and has access to it.
Path to execute tests from this file: 
```
--specs=e2e/features/complaint/evidence/1-uploading-evidence.feature:<Line>
```

**Feature file:** 1-uploading-evidence.feature :
* **Scenario:** User should be able to upload an evidence || **Line:** `8`
* **Scenario:** User should be able to upload more then one evidence with various Evidence type || **Line:** `14`

**Message page**
##These tests describe how Passenger sends message to Administrator and attachs documents. They check if Administrator sees the same message which Passenger sent to him.
Path to execute tests from this file: 
```
--specs=e2e/features/complaint/messages/1-sending-message.feature:<Line>
```
**Feature file:** 1-sending-message.feature :
* **Scenario:** Sending message with additional information || **Line:** `8`

### Dashboard
##These tests describe how user with diffrent role (e.g Administrator, Passenger, SWR, SPTA) signes in. They checks if user can see all column headers on dashboard after signing in.
Path to execute tests from this file: 
```
--specs=e2e/features/dashboard/1-log-in.feature:<Line>
```
**Feature file:** 1-log-in.feature :
* **Scenario:** Log in || **Line:** `8`

##These tests describe how user with diffrent role can filter cases. They check if user can see filtered compliants on dashboard.
Path to execute tests from this file: 
```
--specs=e2e/features/dashboard/2-filters.feature:<Line>
```
**Feature file:** 2-filters.feature :
* **Scenario:** User with <role> should be able to see only these cases which he filtered by <condition> || **Line:** `7`
* **Scenario:** User with role <user> should be able to searching for by <condition> || **Line:** `18`
* **Scenario:** User with role <user> should be able to filtered cases by <condition> || **Line:** `29` 
 
### Miscellaneous
##These tests describe how user register on app. They check if user got confirmation email and registered by unique details and used appropriate password. 
Path to execute tests from this file: 
```
--specs=e2e/features/miscellaneous/1-account-registration.feature:<Line>
```
**Feature file:** 1-account-registration.feature :
* **Scenario:** Sign up validation || **Line:** `4`
* **Scenario:** Sign up and log in || **Line:** `14`

### Permissions
**Complaint**
##These tests check if user with a specific role see appropriate headlines. 
Path to execute tests from this file: 
```
--specs=e2e/features/permissions/complaint/details-screen.feature:<Line>
```
**Feature file:** details-screen.feature :
* **Scenario:** As a <role> I should see the following headlines: <headlines> with sub-headings: <subHeadings> || **Line:** `8`

### Submission-flow
##These tests check if customer got information about his compaint and user with diffrent role is able to see newly created compaints by customer.
Path to execute tests from this file: 
```
--specs=e2e/features/submission-flow/submission-flow.feature:<Line>
```
**Feature file:** submission-flow.feature :
* **Scenario:** Customer should be able to create complaint || **Line:** `8`
* **Scenario:** User with <role> should be able to complete SF and have access to created complaint || **Line:** `14`

### Task-dashboard
##These tests describe how administrator assigns case to SPTA. They check if assigned case is visible to SPTA, and tests check if administrator and SPTA see the approporiate column headers.
Path to execute tests from this file: 
```
--specs=e2e/features/task-dashboard/1-task-dashboard.feature:<Line>
```
**Feature file:** 1-task-dashboard.feature :
* **Scenario:** Assign complaint to SPTA || **Line:** `8`
* **Scenario:** User should see a column with specific headers || **Line:** `14`

### Workflow
##These tests check if status of complaint is appropriate after Passenger upload evidence or missed to this.
Path to execute tests from this file: 
```
--specs=e2e/features/workflow/1-upload-evidence-status.feature:<Line>
```
**Feature file:** 1-upload-evidence-status.feature :
* **Scenario:** The Next Action Box should present 'Upload Evidence' status || **Line:** `7`
* **Scenario:** The Next Action Box should present 'Appeal is being reviewed' status || **Line:** `13`

##These tests check if passenger provided all required information while filling the compliant. They check if administrator see  suitable status of complaint if information were provided or missed.
Path to execute tests from this file: 
```
--specs=e2e/features/workflow/2-acknowledge-appeal-status.feature:<Line>
```
**Feature file:** 2-acknowledge-appeal-status.feature :
* **Scenario:** The Next Action Box should present 'Has the passenger provided all information?' status || **Line:** `8`
* **Scenario:** The Next Action Box should present 'Assign Case' status after No more information is needed from passenger || **Line:** `14`

##These tests check if complaint has suitable status after administrator proceed case with information receive.
Path to execute tests from this file: 
```
--specs=e2e/features/workflow/3-receive-information-status.feature:<Line>
```
**Feature file:** 3-receive-information-status.feature :
* **Scenario:** The Next Action Box should present 'Assign Case' status || **Line:** `8`

##These tests check if complaint has suitable status after administrator assign case to SPTA.
Path to execute tests from this file: 
```
--specs=e2e/features/workflow/4-assign-case-status.feature:<Line>
```
**Feature file:** 4-assign-case-status.feature :
* **Scenario:** The Next Action Box should present 'Investigation' status || **Line:** `8`

##These tests check if complaint has suitable status after SPTA completes investigation.
Path to execute tests from this file: 
```
--specs=e2e/features/workflow/5-investigate-status.feature:<Line>
```
**Feature file:** 5-investigate-status.feature :
* **Scenario:** The Next Action Box should present 'Escalate to TOC' status || **Line:** `8`

##These tests check if complaint has suitable status after SPTA ecsaltes case to TOC.
Path to execute tests from this file: 
```
--specs=e2e/features/workflow/6-excalate-to-toc.feature:<Line>
```
**Feature file:** 6-excalate-to-toc.feature :
* **Scenario:** The Next Action Box should present 'Awaiting TOC response' status || **Line:** `8`

##These tests check if complaint has suitable status after TOC sent response.
Path to execute tests from this file: 
```
--specs=e2e/features/workflow/7-awaiting-resolution-status.feature:<Line>
```
**Feature file:** 7-awaiting-resolution-status.feature :
* **Scenario:** The Next Action Box should present 'Awaiting resolution' status || **Line:** `8`

##These tests check if complaint has outcome message after SPTA created complaint which has got status complete.
Path to execute tests from this file: 
```
--specs=e2e/features/workflow/8-log-outcome-status.feature:<Line>
```
**Feature file:** 8-log-outcome-status.feature :
* **Scenario:** Outcome message should be visible for user who create complaint. Status: complete || **Line:** `8`

A feature file is made up of one or more Scenarios, and a Scenario is made up of the Given-When-Then steps. You can think of a Scenario as a test case and a Feature as a logical set of test cases.

## Scripts
If You want to create compliants, You should use on Your console following command: `npm run createsf`. 
Then 10 compliants will be created.

## CircleCI
You can check very easily tests results in CircleCI. It allows You to see whether or not your Cucumber tests are passing or failing, also it helps You to see what error occured during failling Scenerio. Please look at those 2 films in gif format, which demonstare how to deal with tests results on CircleCI:

![CircleCI](/film.readme/CircleCI.gif)

![CircleCI-failed](/film.readme/CircleCI-failed.gif)

## Technologies
* cucumber - version 5.1.0
* typescript - version 2.7.2
* protractor - version 5.4.2
* chai - version 4.2.0

## Status
Project is: _in progress_.

## Contact
Created by @testarmy - feel free to contact us!
