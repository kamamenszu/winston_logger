# Cucumber test for Transport Focus (TF) portal
This project refers to Transport Focus app. It's uses bdd tests which are readable and common understood by every team member.

## Table of contents
* [Installation](#installation)
* [Executing](#executing)
* [Setup](#setup)
* [Features](#features)
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
Path to execute tests from this file: 
```
--specs=e2e/features/complaint/evidence/1-uploading-evidence.feature:<Line>
```

**Feature file:** 1-uploading-evidence.feature :
* **Scenario:** User should be able to upload an evidence || **Line:** `8`
* **Scenario:** User should be able to upload more then one evidence with various Evidence type || **Line:** `14`

**Message page**
Path to execute tests from this file: 
```
--specs=e2e/features/complaint/messages/1-sending-message.feature:<Line>
```
**Feature file:** 1-sending-message.feature :
* **Scenario:** Sending message with additional information || **Line:** `8`

### Dashboard
Path to execute tests from this file: 
```
--specs=e2e/features/dashboard/1-log-in.feature:<Line>
```
**Feature file:** 1-log-in.feature :
* **Scenario:** Log in || **Line:** `8`

Path to execute tests from this file: 
```
--specs=e2e/features/dashboard/2-filters.feature:<Line>
```
**Feature file:** 2-filters.feature :
* **Scenario:** User with <role> should be able to see only these cases which he filtered by <condition> || **Line:** `7`
* **Scenario:** User with role <user> should be able to searching for by <condition> || **Line:** `18`
* **Scenario:** User with role <user> should be able to filtered cases by <condition> || **Line:** `29` 


## Features
List of features in our project:
* 2 dashboard (module)
  * 1-log-in.feature
  * 2-filters.feature
* 3 miscellaneous (module)
  * 1-account-registration.feature
* 4 permissions (module)
  * complaint
   * details-screen.feature
* 4 scripts (module)
  * create-multiply-complaints.feature
* 5 submission-flow (module)
  * 1-submission-flow.feature
* 6 task-dashboard(module)
 * 1-task-dashboard.feature
* 7 workflow (module)
  * 1-upload-evidence-status.feature
  * 2-acknowledge-appeal-status.feature
  * 3-receive-information-status.feature
  * 4-assign-case-status.feature
  * 5-investigate-status.feature
  * 6-excalate-to-toc.feature
  * 7-awaiting-resolution-status.feature
  * 8-log-outcome-status.feature
  
A feature file is made up of one or more Scenarios, and a Scenario is made up of the Given-When-Then steps. You can think of a Scenario as a test case and a Feature as a logical set of test cases.

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
