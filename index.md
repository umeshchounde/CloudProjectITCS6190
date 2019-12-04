# 1.**Title: Human Activity Recognition using Smartphone and Smartwatch Sensor Data**

## 2. **Project Group:**

Umesh Chounde

Jitesh Golatkar

## 4. **Project Motivation**
<p align="justify">
Today there are billions of people carrying smart devices such as smartphones, fitness gadgets, smartwatches. These sensor-rich gadgets generate larger amount of data that can be utilized using machine learning techniques and big data techniques for mining and deriving meaningful insights about human activity. Some of the common applications that are widely used are fitness trackers, and personal assistant systems for disabled people. We personally used such devices for tracking the activities. We felt that it would be interesting to know how it classify activities and we decided to implement the classification algorithm we studied in this course.</p>

## 3. **Dataset Information**
<p align="justify">
In this project we are using such large dataset and process it using distributed computing frameworks like Spark. We are using couple of the classification algorithms in machine learning to recognize human activity like walking, jogging etc.

5.WISDM dataset consist of raw accelerometer data collected from smartphones and smartwatches. This data is collected from 51 individuals who were assigned to execute 18 different tasks for 3 minutes. Each individual was had smartwatch and smartphone placed on them. There are total 15630426 instances consisting of 6 attributes (subject_id, activity, timestamp, x-reading, y-reading, z-reading). This is a labelled dataset, thus is suitable for classification tasks.

Dataset: 
WISDM Smartphone and Smartwatch Activity and Biometrics Dataset
[DataSetLink](http://archive.ics.uci.edu/ml/datasets/WISDM+Smartphone+and+Smartwatch+Activity+and+Biometrics+Dataset+)

The accelerometer form devices measures the acceleration in 3 dimensions, along with x axis, y axis and z axis.
</p>
* X axis acceleration describes horizontal movement body. 
* Y axis acceleration describes upward and downward movement of body. 
* Z axis acceleration describes forward movement of body.

## **Feature Selection and Data Preparation:**
<p align="justify">
We visualized small set of data for each activity such as walking and jogging we came to know that acceleration of x, y, z axis plays an important role in differentiating the activities. We also considered peak values of accelerations that can help us differentiate activity, because jogging will be having most peak acceleration compared to walking and other activities. In the case of climbing up and down of stairs have periodic actions and we can detect those activities based on activity periodicity. In case of normal activity such as sitting we get constant acceleration for long period.  After thorough study and research we came up with following features might be helpful for building a model. The given data is already sorted according to activity and timestamp of each activity.</p>
    
### Average acceleration:
<p align="justify">
Each activity data records are divided in batches of 200 records. We calculated average acceleration for each axis of the record.</p>
   
### Variance:
<p align="justify">
Each activity data records are divided in batches of 200 records. We calculated variance of acceleration for each axis of the record.</p>
   
### Average absolute difference:
<p align="justify">
We calculated average acceleration for each axis and took absolute difference with average acceleration. Average of this absolute difference is calculated again.</p>
   
### Average resultant acceleration:
<p align="justify">
Average resultant is calculated using the formula. (1/n * sum [√(x² + y² + z²)]) </p>
   
### Average time between peaks 
<p align="justify">
Initially we calculated global maxima for each axis acceleration. Selected all the other local maximum who has value more than 90% of global maxima. Then average of all such values are taken.</p>


## 6. **Algorithms**

### Decision Tree
<p align="justify">
Initially we used Decision Tree for classification of the activities.
</p>

### Naive Bayes Classification 

## 8,9.**Results**
<p align="right">
### Phone Accelerometer
---------------- Classification Using Decision Tree ----------------

Confusion matrix:

322.0  4.0    77.0   8.0    0.0

11.0   391.0  10.0   0.0    1.0

59.0   6.0    321.0  0.0    0.0

10.0   2.0    16.0   311.0  19.0

6.0    3.0    12.0   12.0   357.0

Accuracy = 86.92543411644536

Class 1.000000 precision = 0.789216

Class 1.000000 recall = 0.783455

Class 1.000000 F1 score = 0.786325

Class 2.000000 precision = 0.963054

Class 2.000000 recall = 0.946731

Class 2.000000 F1 score = 0.954823

Class 3.000000 precision = 0.736239

Class 3.000000 recall = 0.831606

Class 3.000000 F1 score = 0.781022

Class 4.000000 precision = 0.939577

Class 4.000000 recall = 0.868715

Class 4.000000 F1 score = 0.902758

Class 5.000000 precision = 0.946950

Class 5.000000 recall = 0.915385

Class 5.000000 F1 score = 0.930900

Weighted precision = 0.874349

Weighted recall = 0.869254

Weighted F1 score = 0.870906

Weighted false positive rate = 0.032965

---------------- Classification Using Naive Bayes ----------------

Confusion matrix:

183.0  26.0   187.0  13.0   2.0

32.0   374.0  5.0    2.0    0.0

63.0   3.0    268.0  27.0   25.0

4.0    14.0   6.0    265.0  69.0

10.0   4.0    9.0    11.0   356.0

Accuracy = 73.8508682328907

Class 1.000000 precision = 0.626712

Class 1.000000 recall = 0.445255

Class 1.000000 F1 score = 0.520626

Class 2.000000 precision = 0.888361

Class 2.000000 recall = 0.905569

Class 2.000000 F1 score = 0.896882

Class 3.000000 precision = 0.564211

Class 3.000000 recall = 0.694301

Class 3.000000 F1 score = 0.622532

Class 4.000000 precision = 0.833333

Class 4.000000 recall = 0.740223

Class 4.000000 F1 score = 0.784024

Class 5.000000 precision = 0.787611

Class 5.000000 recall = 0.912821

Class 5.000000 F1 score = 0.845606

Weighted precision = 0.739407

Weighted recall = 0.738509

Weighted F1 score = 0.732969

Weighted false positive rate = 0.065417
</p>

<p align="right">
### Watch Accelerometer

---------------- Classification Using Decision Tree ----------------

Confusion matrix:

199.0  4.0    104.0  2.0    27.0

2.0    276.0  9.0    9.0    4.0

25.0   1.0    262.0  4.0    8.0

6.0    1.0    17.0   270.0  22.0

7.0    4.0    27.0   26.0   248.0

Accuracy = 80.24296675191816

Class 1.000000 precision = 0.832636

Class 1.000000 recall = 0.592262

Class 1.000000 F1 score = 0.692174

Class 2.000000 precision = 0.965035

Class 2.000000 recall = 0.920000

Class 2.000000 F1 score = 0.941980

Class 3.000000 precision = 0.625298

Class 3.000000 recall = 0.873333

Class 3.000000 F1 score = 0.728790

Class 4.000000 precision = 0.868167

Class 4.000000 recall = 0.854430

Class 4.000000 F1 score = 0.861244

Class 5.000000 precision = 0.802589

Class 5.000000 recall = 0.794872

Class 5.000000 F1 score = 0.798712

Weighted precision = 0.819446

Weighted recall = 0.802430

Weighted F1 score = 0.802527

Weighted false positive rate = 0.048698

---------------- Classification Using Naive Bayes ----------------

Confusion matrix:

64.0  47.0   169.0  2.0    54.0

13.0  280.0  6.0    0.0    1.0

38.0  2.0    208.0  3.0    49.0

18.0  5.0    21.0   207.0  65.0

12.0  7.0    34.0   32.0   227.0

Accuracy = 63.04347826086957

Class 1.000000 precision = 0.441379

Class 1.000000 recall = 0.190476

Class 1.000000 F1 score = 0.266112

Class 2.000000 precision = 0.821114

Class 2.000000 recall = 0.933333

Class 2.000000 F1 score = 0.873635

Class 3.000000 precision = 0.474886

Class 3.000000 recall = 0.693333

Class 3.000000 F1 score = 0.563686

Class 4.000000 precision = 0.848361

Class 4.000000 recall = 0.655063

Class 4.000000 F1 score = 0.739286

Class 5.000000 precision = 0.573232

Class 5.000000 recall = 0.727564

Class 5.000000 F1 score = 0.641243

Weighted precision = 0.629178

Weighted recall = 0.630435

Weighted F1 score = 0.610161

Weighted false positive rate = 0.091249
</p>

## 10.**Project Accomplishments**
<p align="right">
* Implemented Naive Bayes classification algorithm using Spark
* Trained model using Decision Tree classifier in Spark MLib
* Compared classification algorithms for activity classification
</p>

## **Future Scope**
<p align="left">
* Improve Accuracy of classifier
* Improve performance and time in data pre-processing stage
* Determine better feature for sensor data
</p>

## 7.**Software**
<p align="left">
Please find below list of different software we have used for this project
* Spark for data extraction, model training and evaluation 
* AWS EMR cluster for execution of the code
* Spark MLib library for Decision Tree algorithm
</p>

## 11.**Observations**
<p align="left">
* As we have never worked on time series sensor data, it was challenging to decide which feature should be selected for classification.
* Due the structure of raw data, we found challenging to improve performance of data preprocessing using spark
</p>

## **Project Outcome**
<p align="left">
* Learnt to implement classification algorithm in spark 
* Gained Hands on experience with Spark MLib, Dataset API
* Learnt classification using raw sensor data
</p>

## 12.**Work division**
<p align="left">
Umesh:
* Feature Selection and research
* Data Preprocessing
* Report writing

Jitesh:
* Feature Selection and research
* Classification 
* Report writing
</p>

## 13.**References**
<p align="left">
1.Gary M. Weiss, WISDM Smartphone and Smartwatch Activity and Biometrics Dataset

2.Jennifer R. Kwapisz, Gary M. Weiss, Samuel A. Moore, [Activity Recognition using Cell Phone Accelerometers ](http://www.cis.fordham.edu/wisdm/includes/files/sensorKDD-2010.pdf)
</p>
