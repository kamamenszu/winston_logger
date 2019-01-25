# Cucumber test for Transport Focus (DAAS) portal
> This project refers to Transport Focus app. It's uses bdd tests which are readable and common understood by every team member.

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
Once the dependencies are installed, You will then be able to access it at default:
* localhost `https://localhost:8080/`,
* localhost apiUrl`https://localhost:3000/`. 

If Your default localhost apiUrl is diffrent You can change it at file:
* `./protractor.common.conf.js` on line `52`
* `./conf/environment/local.json` on line `19`

## Executing
You can choose 3 different ways to run tests, depends if You want to run all or only particular scenario:
* 1 - to start all tests execution open terminal in main folder and use following command:
`npm run test`
* 2 - to start only tests for workflow (one module) open in main folder and use following command:
`npm run basicWorkflow`
* 3 - to start one Scenerio test from 1 Feature open terminal in main folder and use following command:
`node ./node_modules/protractor/bin/protractor ./protractor.sequential.conf.js --baseUrl='https://daas.resolvertest.com/' --capabilities.chromeOptions.prefs.download.default_directory=`pwd`/tmp --specs=e2e/features/dashboard/1-log-in.feature:8`

NOTICE: If You want to check diffrent Scenerio, change `--specs=e2e/features/../..:..`.
First You should pick module You want to check, e.g. `dashboard` or `complaint` or `workflow`, then write name of feature file, e.g `1-account-registration.feature` or `5-investigate-status.feature` and write line number which Scenerio is in file, e.g `14` or `8`. New path file to check diffrent Scenerio can be `--specs=e2e/features/miscellaneous/1-account-registration.feature:14`.

Look at this short film in gif format, which demonstare how to run only one Scenerio:
![film](/home/testarmy/projekty/daas-testing-master/film.readme/1-log-in.feature:8.gif)

## Features
List of features in our project:
* 1 complaint (module)
  * evidence 
   * 1-uploading-evidence.feature
  * messages
   * 1-sending-message.feature
* 2 dashboard (module)
  * 1-log-in.feature
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
![CircleCI](/home/testarmy/projekty/daas-testing-master/film.readme/CircleCI.gif)
![CircleCI-failed](/home/testarmy/projekty/daas-testing-master/film.readme/CircleCI-failed.gif)

## Technologies
* cucumber - version 5.1.0
* typescript - version 2.7.2
* protractor - version 5.4.2
* chai - version 4.2.0

## Status
Project is: _in progress_.

## Contact
Created by @testarmy - feel free to contact us!
