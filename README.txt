K6 is a powerful framework for performance testing APIs. It uses JavaScript and a BDD-style DSL. 

For more info check the docs - https://k6.io/

Install:
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys 379CE192D401AB61
echo "deb https://dl.bintray.com/loadimpact/deb stable main" | sudo tee -a /etc/apt/sources.list
sudo apt-get update
sudo apt-get install k6

Example Run (runs the basic script with 10 virtual users, ramped up over 30 seconds): 
k6 run basicscript.js --vus 10 --duration 30s


SCRIPTS AND WHAT THEY DO

Basic Script: hits an http endpoint.

Initialise Options: This script sets number of users and duration within the options of the script. This is initialised before the main function is called.

Ramp Stages: Ramps virtual user hits up and down across the length of defined duration

Checks: Run a check to verify the correct status code and also assert the transaction time of the response is less than a set amount (here 200ms)

Note on output: k6 usually uses stdout, it can be configured to use JSON output or influx. To send data to influx instance use - 

k6 run --out influxdb=http://localhost:8086/k6 script.js

The data is then sent to a DB named K6 and can be read with something like Grafana

