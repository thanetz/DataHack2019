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
<a name="Dataset"></a>
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
| type | The device type, one of ("MOBILE_PHONE", "TABLET", "PC", "WATCH", "VOIP", "PRINTER", "IP_CAMERA") |
| model | The device model |
| manufacturer | The device manufacturer |
| operating_system_version | The device Operating System Version |

* Other than "network_id", "device_id" and "type" all fields are optional and can be null

### Example
For example line 3 tells us that in network 1 device with device id of 39399 is of type Mobile Phone manufactured by Apple
TODO: add image

## Sessions Dataset in-depth

### Fields
| Field | Description |
| ------------- |-------------|
| network_id | A numeric network identifier |
| device_id | A numeric device identifier |
| timestamp | The hour for which the sessions data are aggregated |
| host | The domain the device was connected to, if domain is unknown the host ip will be displayed (this field is hashed) |
| host_ip | The ip of the host the device was connected to (this field is hashed) |
| port_dst | The destination port used in the session |
| transport_protocol | The connection protocol - could be TCP or UDP |
| service_device_id | The device id of the destination host that our device was connected to |
| packets_count | Total packets transferred during the aggregated sessions |
| outbound_bytes_count | Total bytes sent during the aggregated sessions |
| inbound_bytes_count | Total bytes received during the aggregated sessions |
| packet_loss | Total packets that were lost during the session |
| retransmit_count | Total packets that were retransmitted during the aggregated sessions |
| latency | Network latency during the aggregated sessions |
| session_count | Count of sessions that this aggregated row holds |
| outbound_packets_count | Total packets sent during the aggregated sessions |
| inbound_packets_count | Total packets received during the aggregated sessions |
| outbound_bytes_max | Max bytes sent in one session of the aggregated sessions |
| outbound_bytes_min | Min bytes sent in one session of the aggregated sessions |
| outbound_bytes_mean | Mean of bytes sent during the aggregated sessions |
| outbound_bytes_median | Median of bytes sent during the aggregated sessions |
| outbound_bytes_stddev | Standard deviation of bytes sent during the aggregated sessions |
| inbound_bytes_max | Max bytes received in one session of the aggregated sessions |
| inbound_bytes_min | Min bytes received in one session of the aggregated sessions |
| inbound_bytes_mean | Mean of bytes received during the aggregated sessions |
| inbound_bytes_median | Median of bytes received during the aggregated sessions |
| inbound_bytes_stddev | Standard deviation of bytes received during the aggregated sessions |
| outbound_packet_size_max | Max packet size sent in one session of the aggregated sessions |
| outbound_packet_size_min | Min packet size sent in one session of the aggregated sessions |
| outbound_packet_size_mean | Mean of packet size sent during the aggregated sessions |
| outbound_packet_size_median | Median of packet size sent during the aggregated sessions |
| outbound_packet_size_stddev | Standard deviation of packet size sent during the aggregated sessions |
| inbound_packet_size_max | Max packet size received in one session of the aggregated sessions |
| inbound_packet_size_min | Min packet size received in one session of the aggregated sessions |
| inbound_packet_size_mean | Mean of packet size received during the aggregated sessions |
| inbound_packet_size_median | Median of packet size received during the aggregated sessions |
| inbound_packet_size_stddev | Standard deviation of packet size received during the aggregated sessions |


* Other than "network_id" and "device_id" all fields are optional and can be null

### Example
For example, line 2 tells us that at 00:00 hours (=midnight) device 139276 was connected to
HYBRID-AD01.armiscorp.com, through port 137, using the UDP protocol. During this hour,
device 139276 sent 438 bytes to HYBRID-AD01.armiscorp.com, and received 455 bytes from it.
A total of 8 packets was transferred.

TODO: add image


## Data Sets Visualizations

TODO: add visualizations

# Example
<a name="Example"></a>
Please look for the example.ipynb notebook in the examples directory. There should be a straightforward approach on anomaly detection using the datasets above.

TODO: add example

# Evaluation
<a name="Evaluation"></a>
As this is an unsupervised challenge, the evaluation process will be a mix of classical leaderboard evaluation and in-person review of the models used. <br>
The final score will be composed of (Sorted descendingly by importance):
* **Leaderboard Evaluation**
Your model results will be matched against a prelabeled dataset - this grading will occur as soon as you'll submit your results for evaluation.
* **Explainability**
Why is this observation an anomaly? Does your model produce a confidence level for each result? Can we calculate the level of importance of this anomaly?
* **Innovation**
Use of an non-trivial algorithm. Creation of ingenious useful features. Any other creative ideas could also be credited with extra scores.

# Submissions
<a name="Submissions"></a>
Please send us the anomaly scores you received for each device along with your code in a zip file. You can submit the results as many times as you wish.

# ENJOY!
