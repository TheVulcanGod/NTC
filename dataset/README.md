# Description of Dataset #

The NIMS Dataset can be obtained from this source : https://projects.cs.dal.ca/projectx/data/NIMS.arff.zip <br />
The original NIMS dataset contains 22 trainable features and 1 class feature. < br />

min_fpkt	:	Minimum forward packet length

mean_fpktl	:	Mean forward packet length

max_fpkt	:	Maximum forward packet length

std_fpktl	:	Standard Deviation for forward packet length


min_bpktl	:	Minimum backward packet length

mean_bpktl	:	Mean backard packet length 

max_bpkl	:	Maximum backward packet length

std_bpktl	:	Standard Deviation of backward packet length

min_fiat	:	Minimum forward inter-packet arrival time

mean_fiat	:	Mean forward inter-packet arrival time


max_fiat	:	maximum forward inter-packet arrival time

std_fiat	:	Standard Deviation for forward inter-packet arrival time

min_biat	:	Minimum forward inter-packet arrival time

mean_biat	: 	Mean backward inter-packet arrival time

max_biat	:	Maximum nackward inter-packet arrival time

std_biat	:	Standard Deviation for backward inter-packet arrival time

duration	: 	Duration

proto		: 	Protocol


total_fpackets	:	Total forward packets

total_fvolume	:	Total forward volume

total_bpackets	:	Total backward packets 

total_bvolume	:	Total backward volume

class		: 	{TELNET,FTP,HTTP,DNS,lime,localForwarding,remoteForwarding,scp,sftp,x11,shell}

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
