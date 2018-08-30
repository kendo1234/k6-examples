SCRIPTS AND WHAT THEY DO

Basic Script: hits an http endpoint with, add users and duration with following command - k6 run --vus 10 --duration 30s basicscript.js

Initialise Options: This script sets number of users and duration within the options of the script. This is initialised before the main function is called.

Ramp Stages: Ramps virtual user hits up and down across the length of defined duration

Checks: Run a check to verify the correct status code and also assert the transaction time of the response is less than a set amount (here 200ms)