SCRIPTS AND WHAT THEY DO

Basic Script: hits an http endpoint with, add users and duration with following command - k6 run --vus 10 --duration 30s basicscript.js

Initialise Options: This script sets number of users and duration within the options of the script. This is initialised before the main function is called.

Ramp Stages: Ramps virtual user hits up and down across the length of defined duration
