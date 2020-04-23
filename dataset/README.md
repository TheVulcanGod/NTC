# Description of Dataset #

The NIMS Dataset can be obtained from this source : https://projects.cs.dal.ca/projectx/data/NIMS.arff.zip <br />
The original NIMS dataset contains 22 trainable features and 1 class feature. In this dataset traffic flow features compose the raw data.  Here the flow is described as the traffic flowing between two hosts at the network layer of the given protocol stack where-in both hosts are using the same five tuple vector (the Source and Destination IP addresses, IP protocol and Source and Destination port numbers) to exchange the traffic. Here the first packet seen will determine the flows beginning while the termination of the given flow depends on either a protocol-based termination mechanism or timeout. Thus, the traffic in the flow can be viewed in the following two ways: 

(i) Traffic from source to destination; and vice-versa 

(ii) Traffic from destination to source.

| Feature        | Description         |
|:------------- |:-------------|
min_fpkt|Minimum forward packet length
mean_fpktl|Mean forward packet length
max_fpkt|Maximum forward packet length
std_fpktl|Standard Deviation for forward packet length
min_bpktl|Minimum backward packet length
mean_bpktl|Mean backard packet length 
max_bpkl|Maximum backward packet length
std_bpktl|Standard Deviation of backward packet length
min_fiat|Minimum forward inter-packet arrival time
mean_fiat|Mean forward inter-packet arrival time
max_fiat|maximum forward inter-packet arrival time
std_fiat|Standard Deviation for forward inter-packet arrival time
min_biat|Minimum forward inter-packet arrival time
mean_biat|Mean backward inter-packet arrival time
max_biat|Maximum nackward inter-packet arrival time
std_biat|Standard Deviation for backward inter-packet arrival time
duration|Duration
proto|Protocol
total_fpackets|Total forward packets
total_fvolume|Total forward volume
total_bpackets|Total backward packets
total_bvolume|Total backward volume
class|TELNET,FTP,HTTP,DNS,lime,localForwarding,remoteForwarding,scp,sftp,x11,shell

### Preprocessing the NIMS.arff dataset ###
The original NIMS.arff file contains repeated rows and several zero columns. The following script  was used to remove all the rows which contained zeros. After doing this to remove the repeated rows  we used Microsoft Excel's 'Delete duplicate rows' feature.<br />
```
import csv
with open('NIMS.csv', 'rb') as inp, open('dataset_original_cleaned.csv', 'wb') as out:
	writer = csv.writer(out)
  	for row in csv.reader(inp):
		if '0' not in row:
    			writer.writerow(row)
```
The **dataset_original_cleaned.csv** is the rendition of NIMS.arff without any zero values and repeated rows with 22 features. While examining features selected by PCA we figured out the packet length statics dimension were not picked up by PCA. Secondly we noticed, the edge features of min observed times were selected as additional discriminators. We saw the usage based features were selected. Hence we did manual feature engineering and arrived at 12 features. From the 22 features as listed in **Description of Dataset** above we removed the min_fpkt, max_fpkt, min_bpkt, max_bpkt, min_fiat, max_fiat, min_biat, max_biat, total_fpackets, total_bpackets, total_fvolume, total_bvolume and protocol. We added : 

fpkt_rate = total_fpackets/duration (forward packet rate) 

bpkt_rate = total_bpackets/duration (backward packet rate)

fbyte_rate = total_fcolume/duration (forward byte rate)

bbyte_rate = total_bvolume/duration (backward byte rate)

*Columns after Feature Engineering:*

| Feature        | Description         |
|:------------- |:-------------|
mean_fpktl|Mean forward packet length
std_fpktl|Standard Deviation for forward packet length
mean_bpktl|Mean backard packet length 
std_bpktl|Standard Deviation of backward packet length
mean_fiat|Mean forward inter-packet arrival time
std_fiat|Standard Deviation for forward inter-packet arrival time
mean_biat|Mean backward inter-packet arrival time
std_biat|Standard Deviation for backward inter-packet arrival time
fpkt_rate|forward packet rate 
bpkt_rate|backward packet rate
fbyte_rate|forward byte rate
bbyte_rate|backward byte rate
class|TELNET,FTP,HTTP,DNS,lime,localForwarding,remoteForwarding,scp,sftp,x11,shell

### Sampling ###
For training and testing purposes the data was sampled to maximum 1000 rows per class to avoid imbalanced data-set problem and bias. 

Class|	Number of Samples in Original Data|No of Samples in Sampled Data|
| :-------------: |:-------------:| :-----:|
DNS|1439|1000
FTP|295|295
HTTP|3470|1000
LIME|14959|1000
LFWD|2521|1000
RFWD|2422|1000
SCP|2411|1000
SFTP|2412|1000
Shell|2004|1000
TELNET|857|857
X11|2013|1000
Total|34803|10152


### Directory Structure ###

```
dataset
├── dataset-12-features
│   ├── class-wise-original
│   │   ├── dns.csv
│   │   ├── ftp.csv
│   │   ├── http.csv
│   │   ├── lime.csv
│   │   ├── localforwarding.csv
│   │   ├── remoteforwarding.csv
│   │   ├── scp.csv
│   │   ├── sftp.csv
│   │   ├── shell.csv
│   │   ├── telnet.csv
│   │   └── x11.csv
│   ├── class-wise-sampled
│   │   ├── dns.csv
│   │   ├── ftp.csv
│   │   ├── http.csv
│   │   ├── lime.csv
│   │   ├── localforwarding.csv
│   │   ├── remoteforwarding.csv
│   │   ├── scp.csv
│   │   ├── sftp.csv
│   │   ├── shell.csv
│   │   ├── telnet.csv
│   │   └── x11.csv
│   ├── original-dataset-cleaned.csv
│   ├── README.md
│   └── sampled-dataset.csv
├── dataset-22-features
│   ├── original-dataset-cleaned.csv
│   ├── README.md
│   └── sampled-dataset.csv
└── README.md
```
