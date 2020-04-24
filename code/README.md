# Code Description #

### List of Notebooks ###
1.MLP-22-features.ipynb <br />
2.MLP-PCA-N=3.ipynb <br />
3.MLP-PCA-N=4.ipynb <br />
4.MLP-PCA-N=5.ipynb <br />
5.MLP-PCA-N=7.ipynb <br />
6.MLP-PCA-N=10.ipynb <br />
7.MLP-16-features-selected-from-DT.ipynb <br />
8.MLP-12-feature-sampled-train-original-test.ipynb <br />
9.DecisionTree-sampled-vs-original-12-features.ipynb <br />
10.Kmeans.ipynb <br />

### Dependencies ###

Jupyter Notebook:



### Description of Notebooks ###

#### 1.MLP-22-features.ipynb ####
This jupyter notebook classifies the 11 classes using the sampled-dataset.

Link to sampled dataset :https://github.com/TheVulcanGod/NTC/blob/master/dataset/dataset-22-features/sampled-dataset.csv 

This dataset has 22 trainable features, 1 class feature and 10152 rows. For more information on this dataset refer https://github.com/TheVulcanGod/NTC/tree/master/dataset#sampling . 

The training and testing split was 80:20.

##### Results #####

```
        class    precision  recall  f1-score   support

           0       1.00      1.00      1.00       199
           1       0.97      0.97      0.97        68
           2       0.97      1.00      0.98       221
           3       0.99      0.99      0.99       165
           4       0.99      0.97      0.98       201
           5       1.00      0.99      1.00       194
           6       0.99      1.00      1.00       192
           7       1.00      0.95      0.98       208
           8       0.95      1.00      0.98       200
           9       0.98      0.99      0.99       200
          10       1.00      0.97      0.99       183

    accuracy                           0.99      2031
   macro avg       0.99      0.99      0.99      2031
weighted avg       0.99      0.99      0.99      2031

Confusion Matrix:

[[199   0   0   0   0   0   0   0   0   0   0]
 [  0  66   0   2   0   0   0   0   0   0   0]
 [  0   0 220   0   1   0   0   0   0   0   0]
 [  0   1   0 164   0   0   0   0   0   0   0]
 [  0   1   5   0 195   0   0   0   0   0   0]
 [  0   0   0   0   0 193   1   0   0   0   0]
 [  0   0   0   0   0   0 192   0   0   0   0]
 [  0   0   0   0   0   0   0 198  10   0   0]
 [  0   0   0   0   0   0   0   0 200   0   0]
 [  0   0   1   0   0   0   0   0   0 199   0]
 [  0   0   0   0   0   0   0   0   0   5 178]]

Map to class id and class name: 
    0:  DNS
    1:  FTP
    2:  HTTP
    3:  TELNET
    4:  lime
    5:  localForwarding
    6:  remoteForwarding
    7:  scp
    8:  sftp
    9:  shell
    10: x11
```

#### 2.MLP-PCA-N=3.ipynb ####
This jupyter notebook classifies the 11 classes using the sampled-dataset but uses only 3/22 trainable features since these 3 were identified as the top 3 features after running PCA.

Features used to train model: **mean_biat, std_fiat , mean_fiat**

Link to sampled dataset :https://github.com/TheVulcanGod/NTC/blob/master/dataset/dataset-22-features/sampled-dataset.csv 

This dataset has 22 trainable features, 1 class feature and 10152 rows. For more information on this dataset refer https://github.com/TheVulcanGod/NTC/tree/master/dataset#sampling . 

The training and testing split was 80:20 ratio of the sampled-dataset.csv(22 features).

##### Results #####

```
        class  precision    recall  f1-score   support

           0       0.71      0.70      0.71       223
           1       1.00      0.01      0.03        67
           2       0.60      0.48      0.53       197
           3       0.75      0.93      0.83       173
           4       0.60      0.53      0.56       197
           5       0.96      0.91      0.94       185
           6       0.99      0.96      0.98       188
           7       0.80      0.30      0.44       210
           8       0.58      1.00      0.73       204
           9       0.64      0.94      0.76       187
          10       0.94      0.93      0.93       200

    accuracy                           0.74      2031
   macro avg       0.78      0.70      0.68      2031
weighted avg       0.76      0.74      0.71      2031

Confusion Matrix:

[[157   0  22  17  25   0   0   0   0   2   0]
 [  4   1  10  13  15   0   0   0   0  23   1]
 [ 19   0  95   3  22   7   0   0   0  45   6]
 [ 11   0   0 161   1   0   0   0   0   0   0]
 [ 25   0  25  21 105   0   0   0   0  19   2]
 [  0   0   0   0   0 169   0  15   1   0   0]
 [  1   0   2   0   0   0 181   1   2   0   1]
 [  1   0   0   1   1   0   1  63 143   0   0]
 [  0   0   1   0   0   0   0   0 203   0   0]
 [  1   0   3   0   6   0   0   0   0 176   1]
 [  1   0   1   0   0   0   1   0   0  12 185]]

Map to class id and class name: 
    0  :  DNS
    1  :  FTP
    2  :  HTTP
    3  :  TELNET
    4  :  lime
    5  :  localForwarding
    6  :  remoteForwarding
    7  :  scp
    8  :  sftp
    9  :  shell
    10 :  x11
```

#### 3.MLP-PCA-N=4.ipynb ####
This jupyter notebook classifies the 11 classes using the sampled-dataset but uses only 4/22 trainable features since these 4 were identified as the top 4 features after running PCA.

Features used to train model: **mean_biat, std_fiat , mean_fiat, total_fvolume**

Link to sampled dataset :https://github.com/TheVulcanGod/NTC/blob/master/dataset/dataset-22-features/sampled-dataset.csv 

This dataset has 22 trainable features, 1 class feature and 10152 rows. For more information on this dataset refer https://github.com/TheVulcanGod/NTC/tree/master/dataset#sampling . 

The training and testing split was 80:20 ratio of the sampled-dataset.csv(22 features).

##### Results #####

```
         class  precision   recall  f1-score   support

           0       0.68      0.81      0.74       178
           1       0.80      0.20      0.32        61
           2       0.60      0.58      0.59       192
           3       0.87      0.88      0.87       175
           4       0.68      0.51      0.58       218
           5       0.99      0.86      0.92       221
           6       0.98      0.91      0.95       200
           7       0.66      0.56      0.60       197
           8       0.62      0.78      0.69       205
           9       0.64      0.93      0.76       196
          10       0.91      0.92      0.92       188

    accuracy                           0.75      2031
   macro avg       0.77      0.72      0.72      2031
weighted avg       0.77      0.75      0.75      2031

Confusion Matrix:

[[145   0  13   3  15   0   0   0   0   2   0]
 [  2  12  13   8   6   0   0   0   0  19   1]
 [ 16   0 112   2  22   0   0   0   0  39   1]
 [  7   0   3 154   8   0   0   0   0   3   0]
 [ 34   3  28  11 112   0   1   1   0  27   1]
 [  0   0   1   0   0 190   0  22   8   0   0]
 [  3   0   4   0   2   0 182   0   4   3   2]
 [  1   0   1   0   0   1   0 110  82   0   2]
 [  0   0   2   0   0   0   0  34 160   0   9]
 [  1   0   9   0   0   0   2   0   0 183   1]
 [  3   0   0   0   0   0   0   0   2  10 173]]

Map to class id and class name: 
    0  :  DNS
    1  :  FTP
    2  :  HTTP
    3  :  TELNET
    4  :  lime
    5  :  localForwarding
    6  :  remoteForwarding
    7  :  scp
    8  :  sftp
    9  :  shell
    10 :  x11
```

#### 4.MLP-PCA-N=5.ipynb ####
This jupyter notebook classifies the 11 classes using the sampled-dataset but uses only 5/22 trainable features since these 5 were identified as the top 5 features after running PCA.

Features used to train model: **mean_fiat, std_fiat, mean_biat, std_biat, total_bpackets**

Link to sampled dataset :https://github.com/TheVulcanGod/NTC/blob/master/dataset/dataset-22-features/sampled-dataset.csv 

This dataset has 22 trainable features, 1 class feature and 10152 rows. For more information on this dataset refer https://github.com/TheVulcanGod/NTC/tree/master/dataset#sampling . 

The training and testing split was 80:20 ratio of the sampled-dataset.csv(22 features).

##### Results #####

```
         class   precision  recall  f1-score   support

           0       0.84      0.76      0.80       208
           1       0.88      0.25      0.39        55
           2       0.63      0.64      0.63       193
           3       0.85      0.96      0.90       174
           4       0.75      0.73      0.74       199
           5       0.97      0.89      0.93       215
           6       0.97      0.95      0.96       204
           7       0.64      0.70      0.67       191
           8       0.75      0.74      0.75       217
           9       0.71      0.88      0.79       190
          10       0.97      0.97      0.97       185

    accuracy                           0.81      2031
   macro avg       0.81      0.77      0.78      2031
weighted avg       0.81      0.81      0.80      2031

Confusion Matrix:

[[159   0  16  11  19   0   0   0   0   2   1]
 [  2  14   7   5   4   0   0   0   0  22   1]
 [ 11   2 124   2  20   1   1   0   0  31   1]
 [  1   0   3 167   0   0   0   0   0   3   0]
 [ 16   0  22  11 145   0   1   1   0   2   1]
 [  0   0   0   0   0 192   0  21   2   0   0]
 [  0   0   2   0   1   0 194   0   1   4   2]
 [  0   0   1   0   1   4   2 134  49   0   0]
 [  0   0   2   0   0   0   0  55 160   0   0]
 [  0   0  21   0   2   0   0   0   0 167   0]
 [  0   0   0   0   2   0   1   0   0   3 179]]
Map to class id and class name: 
    0  :  DNS
    1  :  FTP
    2  :  HTTP
    3  :  TELNET
    4  :  lime
    5  :  localForwarding
    6  :  remoteForwarding
    7  :  scp
    8  :  sftp
    9  :  shell
    10 :  x11
```

#### 5.MLP-PCA-N=7.ipynb ####
This jupyter notebook classifies the 11 classes using the sampled-dataset but uses only 7/22 trainable features since these 7 were identified as the top 7 features after running PCA.

Features used to train model: **mean_fiat, std_fiat, mean_biat, std_biat, total_bpackets, total_fpackets, total_fvolume**

Link to sampled dataset :https://github.com/TheVulcanGod/NTC/blob/master/dataset/dataset-22-features/sampled-dataset.csv 

This dataset has 22 trainable features, 1 class feature and 10152 rows. For more information on this dataset refer https://github.com/TheVulcanGod/NTC/tree/master/dataset#sampling . 

The training and testing split was 80:20 ratio of the sampled-dataset.csv(22 features).

##### Results #####

```
        class    precision  recall  f1-score   support

           0       0.78      0.83      0.80       205
           1       0.89      0.27      0.41        63
           2       0.66      0.62      0.64       197
           3       0.90      0.91      0.91       179
           4       0.72      0.70      0.71       202
           5       0.89      0.99      0.94       189
           6       0.99      0.95      0.97       190
           7       0.86      0.81      0.84       203
           8       0.84      0.79      0.81       196
           9       0.72      0.90      0.80       200
          10       0.95      0.99      0.97       207

    accuracy                           0.83      2031
   macro avg       0.84      0.80      0.80      2031
weighted avg       0.83      0.83      0.82      2031

Confusion Matrix:

[[171   2   9   3  16   0   0   0   0   4   0]
 [  7  17   9   3   6   0   0   0   0  19   2]
 [ 11   0 122   3  17   3   1   0   0  37   3]
 [ 11   0   0 163   3   0   0   0   0   2   0]
 [ 18   0  23   9 142   0   0   0   0   5   5]
 [  0   0   0   0   0 187   0   2   0   0   0]
 [  1   0   4   0   4   0 180   0   0   1   0]
 [  0   0   3   0   1   4   0 165  29   0   1]
 [  1   0   1   0   0  15   0  25 154   0   0]
 [  0   0  15   0   6   0   0   0   0 179   0]
 [  0   0   0   0   1   0   0   0   0   2 204]]
 
Map to class id and class name: 
    0  :  DNS
    1  :  FTP
    2  :  HTTP
    3  :  TELNET
    4  :  lime
    5  :  localForwarding
    6  :  remoteForwarding
    7  :  scp
    8  :  sftp
    9  :  shell
    10 :  x11
```
#### 6.MLP-PCA-N=10.ipynb ####
This jupyter notebook classifies the 11 classes using the sampled-dataset but uses only 10/22 trainable features since these 10 were identified as the top 10 features after running PCA.

Features used to train model: **min_fiat, mean_fiat, std_fiat, min_biat, mean_biat, std_biat,  total_bpackets, total_fpackets, total_fvolume, proto**

Link to sampled dataset :https://github.com/TheVulcanGod/NTC/blob/master/dataset/dataset-22-features/sampled-dataset.csv 

This dataset has 22 trainable features, 1 class feature and 10152 rows. For more information on this dataset refer https://github.com/TheVulcanGod/NTC/tree/master/dataset#sampling . 

The training and testing split was 80:20 ratio of the sampled-dataset.csv(22 features).

##### Results #####

```
          class   precision recall  f1-score   support

           0       0.96      0.98      0.97       196
           1       0.78      0.26      0.40        68
           2       0.71      0.80      0.75       198
           3       0.96      0.98      0.97       164
           4       0.93      0.86      0.89       189
           5       0.98      0.96      0.97       203
           6       1.00      0.97      0.98       209
           7       0.85      0.72      0.78       200
           8       0.75      0.86      0.80       200
           9       0.79      0.91      0.84       220
          10       0.96      0.97      0.97       184

    accuracy                           0.88      2031
   macro avg       0.88      0.84      0.85      2031
weighted avg       0.88      0.88      0.87      2031

Confusion Matrix:

[[192   0   0   0   4   0   0   0   0   0   0]
 [  0  18  29   1   3   0   0   0   0  17   0]
 [  0   4 158   3   4   0   0   0   0  26   3]
 [  0   0   3 160   1   0   0   0   0   0   0]
 [  7   1  10   3 163   0   0   0   0   2   3]
 [  0   0   1   0   0 194   0   0   7   1   0]
 [  0   0   1   0   1   0 202   0   0   5   0]
 [  0   0   1   0   0   4   0 144  51   0   0]
 [  0   0   0   0   0   0   0  26 173   1   0]
 [  0   0  18   0   0   0   0   0   0 201   1]
 [  0   0   2   0   0   0   0   0   0   3 179]]
 
Map to class id and class name: 
    0  :  DNS
    1  :  FTP
    2  :  HTTP
    3  :  TELNET
    4  :  lime
    5  :  localForwarding
    6  :  remoteForwarding
    7  :  scp
    8  :  sftp
    9  :  shell
    10 :  x11
```
#### 7.MLP-16-features-selected-from-DT.ipynb ####
This jupyter notebook classifies the 11 classes using the sampled-dataset but uses only 16/22 trainable features since only these 16 were present in the nodes of the decision tree which was used to classify the sampled-dataset with 22 features.

The decision tree was made using WEKA. More information on WEKA can be found here: https://www.cs.waikato.ac.nz/ml/weka/

**Decision Tree Result:**

```
=== Run information ===

Scheme:       weka.classifiers.trees.J48 -C 0.25 -M 2
Relation:     sampled-dataset
Instances:    10152
Attributes:   23
              min_fpktl
              mean_fpktl
              max_fpktl
              std_fpktl
              min_bpktl
              mean_bpktl
              max_bpktl
              std_bpktl
              min_fiat
              mean_fiat
              max_fiat
              std_fiat
              min_biat
              mean_biat
              max_biat
              std_biat
              duration
              proto
              total_fpackets
              total_fvolume
              total_bpackets
              total_bvolume
              class
Test mode:    split 80.0% train, remainder test

=== Classifier model (full training set) ===

J48 pruned tree
------------------

mean_fpktl <= 1404
|   max_fpktl <= 175
|   |   proto <= 6
|   |   |   max_fpktl <= 55
|   |   |   |   min_fiat <= 137
|   |   |   |   |   max_fpktl <= 50: TELNET (5.0)
|   |   |   |   |   max_fpktl > 50: HTTP (4.0)
|   |   |   |   min_fiat > 137: TELNET (852.0)
|   |   |   max_fpktl > 55
|   |   |   |   max_bpktl <= 277
|   |   |   |   |   max_bpktl <= 52: lime (4.0)
|   |   |   |   |   max_bpktl > 52: FTP (295.0)
|   |   |   |   max_bpktl > 277: HTTP (6.0/1.0)
|   |   proto > 6: DNS (1000.0)
|   max_fpktl > 175
|   |   min_fiat <= 9
|   |   |   proto <= 6
|   |   |   |   max_fpktl <= 1240: HTTP (27.0)
|   |   |   |   max_fpktl > 1240
|   |   |   |   |   max_biat <= 716039
|   |   |   |   |   |   max_bpktl <= 926
|   |   |   |   |   |   |   min_biat <= 84: scp (4.0)
|   |   |   |   |   |   |   min_biat > 84: sftp (2.0/1.0)
|   |   |   |   |   |   max_bpktl > 926
|   |   |   |   |   |   |   mean_bpktl <= 222: x11 (2.0)
|   |   |   |   |   |   |   mean_bpktl > 222: HTTP (4.0)
|   |   |   |   |   max_biat > 716039: x11 (980.0)
|   |   |   proto > 6: lime (51.0)
|   |   min_fiat > 9
|   |   |   min_fpktl <= 51
|   |   |   |   std_bpktl <= 136
|   |   |   |   |   std_fpktl <= 8: HTTP (15.0)
|   |   |   |   |   std_fpktl > 8
|   |   |   |   |   |   total_fvolume <= 1117: HTTP (10.0)
|   |   |   |   |   |   total_fvolume > 1117: lime (748.0/1.0)
|   |   |   |   std_bpktl > 136
|   |   |   |   |   min_biat <= 58: lime (103.0)
|   |   |   |   |   min_biat > 58
|   |   |   |   |   |   min_fpktl <= 40
|   |   |   |   |   |   |   min_fiat <= 1317
|   |   |   |   |   |   |   |   min_biat <= 2938: HTTP (331.0)
|   |   |   |   |   |   |   |   min_biat > 2938
|   |   |   |   |   |   |   |   |   total_bpackets <= 6: HTTP (12.0/1.0)
|   |   |   |   |   |   |   |   |   total_bpackets > 6: lime (2.0)
|   |   |   |   |   |   |   min_fiat > 1317
|   |   |   |   |   |   |   |   mean_fiat <= 170106: HTTP (16.0/2.0)
|   |   |   |   |   |   |   |   mean_fiat > 170106: lime (26.0)
|   |   |   |   |   |   min_fpktl > 40: lime (18.0)
|   |   |   min_fpktl > 51
|   |   |   |   max_fpktl <= 690
|   |   |   |   |   min_fiat <= 7444: HTTP (393.0)
|   |   |   |   |   min_fiat > 7444: lime (4.0)
|   |   |   |   max_fpktl > 690
|   |   |   |   |   max_fpktl <= 692
|   |   |   |   |   |   min_fiat <= 58
|   |   |   |   |   |   |   min_fiat <= 38: shell (20.0)
|   |   |   |   |   |   |   min_fiat > 38: remoteForwarding (20.0)
|   |   |   |   |   |   min_fiat > 58
|   |   |   |   |   |   |   max_bpktl <= 719
|   |   |   |   |   |   |   |   total_fpackets <= 23
|   |   |   |   |   |   |   |   |   mean_fpktl <= 140
|   |   |   |   |   |   |   |   |   |   mean_fiat <= 79899: sftp (4.0/1.0)
|   |   |   |   |   |   |   |   |   |   mean_fiat > 79899: scp (10.0/1.0)
|   |   |   |   |   |   |   |   |   mean_fpktl > 140: shell (13.0/2.0)
|   |   |   |   |   |   |   |   total_fpackets > 23: x11 (4.0)
|   |   |   |   |   |   |   max_bpktl > 719
|   |   |   |   |   |   |   |   min_fiat <= 218
|   |   |   |   |   |   |   |   |   mean_fpktl <= 175
|   |   |   |   |   |   |   |   |   |   mean_bpktl <= 130
|   |   |   |   |   |   |   |   |   |   |   std_fpktl <= 189: x11 (3.0)
|   |   |   |   |   |   |   |   |   |   |   std_fpktl > 189: shell (6.0)
|   |   |   |   |   |   |   |   |   |   mean_bpktl > 130: shell (924.0/5.0)
|   |   |   |   |   |   |   |   |   mean_fpktl > 175
|   |   |   |   |   |   |   |   |   |   std_biat <= 153491
|   |   |   |   |   |   |   |   |   |   |   mean_fpktl <= 203: shell (37.0/1.0)
|   |   |   |   |   |   |   |   |   |   |   mean_fpktl > 203: x11 (4.0/1.0)
|   |   |   |   |   |   |   |   |   |   std_biat > 153491: x11 (3.0)
|   |   |   |   |   |   |   |   min_fiat > 218
|   |   |   |   |   |   |   |   |   min_fiat <= 1167: shell (9.0/2.0)
|   |   |   |   |   |   |   |   |   min_fiat > 1167: scp (3.0/1.0)
|   |   |   |   |   max_fpktl > 692
|   |   |   |   |   |   min_biat <= 39: lime (32.0)
|   |   |   |   |   |   min_biat > 39
|   |   |   |   |   |   |   mean_fpktl <= 910: HTTP (187.0/2.0)
|   |   |   |   |   |   |   mean_fpktl > 910: lime (3.0/1.0)
mean_fpktl > 1404
|   max_fpktl <= 1500
|   |   max_bpktl <= 769
|   |   |   mean_bpktl <= 57: scp (978.0/1.0)
|   |   |   mean_bpktl > 57
|   |   |   |   std_bpktl <= 45: sftp (987.0)
|   |   |   |   std_bpktl > 45
|   |   |   |   |   min_fiat <= 5
|   |   |   |   |   |   min_biat <= 59: scp (2.0)
|   |   |   |   |   |   min_biat > 59: sftp (6.0/1.0)
|   |   |   |   |   min_fiat > 5: scp (2.0)
|   |   max_bpktl > 769
|   |   |   mean_fiat <= 10898: localForwarding (991.0)
|   |   |   mean_fiat > 10898
|   |   |   |   max_fpktl <= 1492: lime (5.0)
|   |   |   |   max_fpktl > 1492: localForwarding (5.0)
|   max_fpktl > 1500: remoteForwarding (980.0)

Number of Leaves  : 	52

Size of the tree : 	103


Time taken to build model: 0.3 seconds

=== Evaluation on test split ===

Time taken to test model on test split: 0.02 seconds

=== Summary ===

Correctly Classified Instances        2012               99.1133 %
Incorrectly Classified Instances        18                0.8867 %
Kappa statistic                          0.9902
Mean absolute error                      0.0019
Root mean squared error                  0.0388
Relative absolute error                  1.147  %
Root relative squared error             13.5395 %
Total Number of Instances             2030     
```

Features used to train model: **min_fpktl, mean_fpktl, max_fpktl, std_fpktl, mean_bpktl, max_bpktl, std_bpktl, min_fiat,  mean_fiat, min_biat, max_biat, std_biat, proto, total_fpackets, total_fvolume, total_bpackets**

Link to sampled dataset :https://github.com/TheVulcanGod/NTC/blob/master/dataset/dataset-22-features/sampled-dataset.csv 

This dataset has 22 trainable features, 1 class feature and 10152 rows. For more information on this dataset refer https://github.com/TheVulcanGod/NTC/tree/master/dataset#sampling . 

The training and testing split was 80:20 ratio of the sampled-dataset.csv(22 features).

##### Results #####

```

        class    precision  recall  f1-score   support

           0       1.00      1.00      1.00       209
           1       0.97      0.94      0.95        67
           2       0.96      0.99      0.97       171
           3       0.98      0.99      0.99       170
           4       1.00      0.96      0.98       225
           5       1.00      0.99      1.00       199
           6       1.00      1.00      1.00       201
           7       0.99      0.98      0.98       186
           8       0.99      0.99      0.99       232
           9       0.98      0.99      0.99       192
          10       0.99      0.98      0.99       179

    accuracy                           0.99      2031
   macro avg       0.99      0.98      0.99      2031
weighted avg       0.99      0.99      0.99      2031

Confusion Matrix:

[[209   0   0   0   0   0   0   0   0   0   0]
 [  0  63   0   4   0   0   0   0   0   0   0]
 [  0   0 170   0   1   0   0   0   0   0   0]
 [  0   1   0 169   0   0   0   0   0   0   0]
 [  0   1   7   0 217   0   0   0   0   0   0]
 [  0   0   0   0   0 198   1   0   0   0   0]
 [  0   0   0   0   0   0 200   0   0   1   0]
 [  0   0   1   0   0   0   0 182   3   0   0]
 [  0   0   0   0   0   0   0   2 230   0   0]
 [  0   0   0   0   0   0   0   0   0 191   1]
 [  0   0   0   0   0   0   0   0   0   3 176]]
 
Map to class id and class name: 
    0  :  DNS
    1  :  FTP
    2  :  HTTP
    3  :  TELNET
    4  :  lime
    5  :  localForwarding
    6  :  remoteForwarding
    7  :  scp
    8  :  sftp
    9  :  shell
    10 :  x11
```
#### 8.MLP-12-feature-sampled-train-original-test.ipynb ####
This jupyter notebook classifies the 11 classes using the sampled-dataset(12 features). The aim of this experiment is to find out how good our sampling was and how close is it to the original-dataset-cleaned. We use the sampled and original dataset which were feature engineered to have 12 features.

For information on Feature Engineering: https://github.com/TheVulcanGod/NTC/tree/master/dataset#feature-engineering

Link to sampled dataset(12 features): https://github.com/TheVulcanGod/NTC/blob/master/dataset/dataset-12-features/sampled-dataset.csv

The sampled dataset has 12 trainable features and 1 class feature. It has 10152 rows.

Link to original dataset(12 features): https://github.com/TheVulcanGod/NTC/blob/master/dataset/dataset-12-features/original-dataset-cleaned.csv 

The original dataset has 12 trainable features and 1 class feature. It has 34803 rows.

Training data: 100% of sampled-dataset.csv

Testing data: 100% of original-dataset-cleaned.csv

##### Results #####

```
        class    precision  recall  f1-score   support

           0       0.98      1.00      0.99      1439
           1       0.84      0.96      0.89       295
           2       0.79      0.95      0.87      3470
           3       0.92      0.99      0.96       857
           4       1.00      0.94      0.97     14959
           5       0.99      1.00      0.99      2521
           6       0.99      0.98      0.99      2422
           7       1.00      0.92      0.96      2411
           8       0.94      0.99      0.96      2412
           9       0.94      0.99      0.96      2004
          10       0.98      0.98      0.98      2013

    accuracy                           0.96     34803
   macro avg       0.94      0.97      0.96     34803
weighted avg       0.96      0.96      0.96     34803

Confusion Matrix:

[[ 1435     3     0     0     1     0     0     0     0     0     0]
 [   10   284     0     0     1     0     0     0     0     0     0]
 [    1    10  3299    14    51     0     1     0     0    72    22]
 [    0     9     0   848     0     0     0     0     0     0     0]
 [   15    34   754    54 14059     0    14     0     0    24     5]
 [    0     0     1     0     1  2515     0     0     2     2     0]
 [    0     0    29     0    13     0  2371     0     0     9     0]
 [    0     0    35     1     0     8     0  2219   147     0     1]
 [    0     0    14     0     1    12     0     5  2377     2     1]
 [    0     0    13     0     1     0     0     0     0  1984     6]
 [    0     0     7     0     0     0     0     0     3    26  1977]]
 
Map to class id and class name: 
    0  :  DNS
    1  :  FTP
    2  :  HTTP
    3  :  TELNET
    4  :  lime
    5  :  localForwarding
    6  :  remoteForwarding
    7  :  scp
    8  :  sftp
    9  :  shell
    10 :  x11
```
Since the testimg accuracy is 96% we can say that the samplimg was good and it is a good representation of the original data.

#### 9.DecisionTree-sampled-vs-original-12-features.ipynb ####

This jupyter notebook classifies the 11 classes using the sampled-dataset(12 features) using a decision tree. This decision tree is then used to test the original-dataset(12 features). The aim of this experiment is to find out how good our sampling was and how close is it to the original-dataset-cleaned. We use the sampled and original dataset which were feature engineered to have 12 features.

For information on Feature Engineering: https://github.com/TheVulcanGod/NTC/tree/master/dataset#feature-engineering

Link to sampled dataset(12 features): https://github.com/TheVulcanGod/NTC/blob/master/dataset/dataset-12-features/sampled-dataset.csv

The sampled dataset has 12 trainable features and 1 class feature. It has 10152 rows.

Link to original dataset(12 features): https://github.com/TheVulcanGod/NTC/blob/master/dataset/dataset-12-features/original-dataset-cleaned.csv 

The original dataset has 12 trainable features and 1 class feature. It has 34803 rows.

Data used to build the decision tree    :sampled-dataset.csv 

Data used to test the decision tree     :original-dataset-cleaned.csv

**Built Decision Tree:**

![DT](https://user-images.githubusercontent.com/29172884/80209408-aa8b0f80-864f-11ea-8de6-cad70bdc4a91.png)
```
Map to class id and class name: 
    0  :  DNS
    1  :  FTP
    2  :  HTTP
    3  :  TELNET
    4  :  lime
    5  :  localForwarding
    6  :  remoteForwarding
    7  :  scp
    8  :  sftp
    9  :  shell
    10 :  x11
```

##### Results #####

```
Accuracy :  97.03761170014079
Report :                    precision    recall  f1-score   support

             DNS       1.00      1.00      1.00      1439
             FTP       0.94      1.00      0.97       295
            HTTP       0.85      0.94      0.90      3470
          TELNET       1.00      1.00      1.00       857
            lime       0.99      0.95      0.97     14959
 localForwarding       0.98      0.99      0.99      2521
remoteForwarding       0.98      0.99      0.99      2422
             scp       0.97      1.00      0.98      2411
            sftp       0.98      0.99      0.99      2412
           shell       0.98      0.99      0.98      2004
             x11       0.96      0.99      0.97      2013

        accuracy                           0.97     34803
       macro avg       0.97      0.99      0.98     34803
    weighted avg       0.97      0.97      0.97     34803

Confusion Matrix:
 [[ 1438     1     0     0     0     0     0     0     0     0     0]
 [    0   295      0     0     0     0     0     0     0     0     0]
 [    0     1   3269     0   110     1     7     9     6    19    48]
 [    0     0      0   857     0     0     0     0     0     0     0]
 [    2    16    530     0 14239    25    38    41    30    10    28]
 [    0     0      2     0     0  2506     0     5     8     0     0]
 [    0     0      7     0     5     0  2406     1     0     3     0]
 [    0     0      2     0     2     3     0  2399     3     1     1]
 [    0     0      4     0     2     8     0     9  2389     0     0]
 [    1     0      6     0     4     0     1     1     1  1980    10]
 [    0     0     10     0     3     2     0     0     0     4  1994]]
```
Since the testing accuracy is 97% we can say that the samplimg was good and it is a good representation of the original data.
