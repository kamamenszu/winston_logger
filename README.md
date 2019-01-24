# Cucumber test for Transport Focus (DAAS) portal
> This project refers to Transport Focus app. It's uses bdd tests which are readable and common understood by every team member.

## Table of contents
* [Installation](#installation)
* [Executing tests](#executing tests on Linux and Chrome)
* [Setup](#setup)
* [Technologies](#technologies)
* [Features](#features)
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

## Executing tests on Linux and Chrome
You can choose 3 different ways to run tests, depends if You want to run all or only particular scenario:
* 1 - to start all tests execution open terminal in main folder and use following command
`npm run test`
* 2 - to start only tests for workflow (one module) open in main folder and use following command
`npm run basicWorkflow`
* 3 - to start one scenerio test from 1 feature open terminal in main folder and use following command
`node ./node_modules/protractor/bin/protractor ./protractor.sequential.conf.js --baseUrl='https://daas.resolvertest.com/' --capabilities.chromeOptions.prefs.download.default_directory=`pwd`/tmp --specs=e2e/features/dashboard/1-log-in.feature:8`
Look at this short film in gif format, which demonstare how to run only one scenerio:
![tekst alternatywny](/home/testarmy/projekty/daas-testing-master/film.readme)

## Technologies
* cucumber - version 5.1.0
* typescript - version 2.7.2
* protractor - version 5.4.2
* chai - version 4.2.0

## Features
List of features ready and TODOs for future development
* Awesome feature 1
* Awesome feature 2
* Awesome feature 3

To-do list:
* Wow improvement to be done 1
* Wow improvement to be done 2

## Status
Project is: _in progress_.

## Contact
Created by testarmy - feel free to contact us!
