# DATAHACK 2019

![Armis](/Armis-LinkedIn-Banner-IMG.png?raw=true "Armis")

# Devices Gone Rogue Challenge
Ever wondered what would happen if you just plug in that seemingly innocent USB you found laying around? You’re about to find out! In this devices-gone-rogue challenge - should you choose to accept it - you will gain access to traffic data of ~ 1M devices, and will be tasked with finding the devices that, well, misbehave. This challenge, provided by Armis, is fully unsupervised - so put your anomaly belt on and get to it!


# Table of Contents  
[Dataset](#Dataset)  
[Example](#Example)  
[Evaluation](#Evaluation)  
[Submissions](#Submissions)

# Dataset
<a name="Dataset"/>
We will used devices information and network traffic from several different networks:
* **Devices.csv** - Data of devices and their appropriate type, manufacturer and model.
* **Sessions.csv** - Details of the connections between a device and external or internal hosts,
aggregated by hours (each row aggregates data from several sessions).

## Device Dataset in-depth
### Fields
| Field | Description |
| ------------- |-------------|
| network_id | A numeric network identifier |
| device_id | A numeric device identifier |
| type | The device type, one of ("MOBILE_PHONE", "LAPTOP", "TABLET", "DESKTOP", "WATCH", "VOIP", "PRINTER", "IP_CAMERA") |
| model | The device model |
| manufacturer | The device manufacturer |
| operating_system_version | The device Operating System Version |

* Other than "network_id", "device_id" and "type" all fields are optional and can be null

### Example
For example line 3 tells us that in network 1 device with device id of 39399 is of type Mobile Phone manufactured by Apple


## Sessions Dataset in-depth

## Data Sets Visualizations

# Example
<a name="Example"/>
Please look for the example.ipynb notebook in the examples directory. There should be a straightforward approach on anomaly detection using the datasets above.

# Evaluation
<a name="Evaluation"/>
As this is an unsupervised challenge, the evaluation process will be a mix of classical leaderboard evaluation and in-person review of the models used. <br>
The final score will be composed of (Sorted descendingly by importance):
* **Leaderboard Evaluation**
Your model results will be matched against a prelabeled dataset - this grading will occur as soon as you'll submit your results for evaluation.
* **Explainability**
Why is this observation an anomaly? Does your model produce a confidence level for each result? Can we calculate the level of importance of this anomaly?
* **Innovation**
Use of an non-trivial algorithm. Creation of ingenious useful features. Any other creative ideas could also be credited with extra scores.

# Submissions
<a name="Submissions"/>
Please send us the anomaly scores you received for each device along with your code in a zip file. You can submit the results as many times as you wish.

# ENJOY!
