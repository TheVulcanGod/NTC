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

