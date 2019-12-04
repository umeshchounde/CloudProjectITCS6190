# 1.**Title: Human Activity Recognition using Smartphone and Smartwatch Sensor Data**

## 2. **Project Group:**

Umesh Chounde

Jitesh Golatkar

## 4. **Project Motivation**

Today there are billions of people carrying smart devices such as smartphones, fitness gadgets, smartwatches. These sensor-rich gadgets generates larger amount of data that can be utilized using machine learning techniques and big data techniques for mining and deriving meaningful insights about human activity. Some of the common applications that are widely used are fitness trackers, and personal assistant systems for dissabled people. We personally used such devices for tracking the activities. We felt that it would be interesting to know how it classify activities and we decided to implement the classification algorithm we studied in this course.

## 3. **Dataset Information**
In this project we are using such large dataset and process it using distributed computing frameworks like Spark. We are using couple of the classification algorithms in machine learning to recognise human activity like walking, jogging etc.

5.WISDM dataset consist of raw accelerometer  data collected from smartphones and smartwatches. This data is collected from 51 individuals who were assigned to execute 18 different tasks for 3 minutes. Each individual was had smartwatch and smartphone placed on them. There are total 15630426 instances consisting of 6 attributes (subject_id, activity, timestamp, x-reading, y-reading, z-reading). This is a labelled dataset, thus is suitable for classification tasks.

DataSet: 
WISDM Smartphone and Smartwatch Activity and Biometrics Dataset
[DataSetLink](http://archive.ics.uci.edu/ml/datasets/WISDM+Smartphone+and+Smartwatch+Activity+and+Biometrics+Dataset+)

The accelerometer form devices measures the accelaration in 3 dimessions, along with x axis, y axis and z axis. 
X axis accelaration describes horizontal movement body. 
Y axis accelaration describes upward and downward movement of body. 
Z axis accelaration describes forward movement of body.

## **Feature Selection and Data Preparation:**

   We vizualised small set of data for each activity such as walking and jogging we came to know that accelaration of x, y, z axis plays an important role in differentiating the activities. We also considered peak values of accelarations that can help us differentiate activity, beacause jogging will be having most peak accelaration compared to walking and other activities. In the case of climbing up and down of stairs have periodic actions and we can detect those activities on the basis of activity periodicity. In case of normal activity such as sitting we get constant accelaration for long period.  After thorough study and research we came up with following features might be helpful for building a model. The given data is already sorted according to activity and timestamp of each activity.
    
### Average acceleration:

Each activity data records are divided in batches of 200 records. We calculated average accelaration for each axis of the record
   
### Variance:

Each activity data records are divided in batches of 200 records. We calculated variance of accelaration for each axis of the record
   
### Average absolute difference:

We calculated average accelaration for each axis and took absolute difference with average accelaration. Average of this absolute difference is calculated again.
   
### Average resultant acceleration:

Average resultant is calculated using the formula.(1/n * sum [√(x² + y² + z²)])
   
### Average time between peaks 

Initially we calculated global maxima for each axis accelaration. Selected all the other local maximum who has value more than 90% of global maxima. Then average of all such values are taken.


## 6. **Algorithms**

### Decision Tree

Initially we used Decision Tree for classifiaction of the activities.

### Naive Bayes Classification 

## 8,9.**Results**

### Phone Acelerometer
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



### Watch Acelerometer

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


## 10.**Project goal achieved?**

## 7.**Software**

Please find below list of different softwares we have used for this project
1. Spark for data extraction, model training and evaluation 
2. AWS EMR cluster for execution of the code
3. Spark MLib library for Decision Tree algorithm


11.**Observations**

12.**Work division**

13.**References**

code snipets




You can use the [editor on GitHub](https://github.com/umeshchounde/CloudProjectITCS6190/edit/master/index.md) to maintain and preview the content for your website in Markdown files.

Whenever you commit to this repository, GitHub Pages will run [Jekyll](https://jekyllrb.com/) to rebuild the pages in your site, from the content in your Markdown files.

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Jekyll Themes

Your Pages site will use the layout and styles from the Jekyll theme you have selected in your [repository settings](https://github.com/umeshchounde/CloudProjectITCS6190/settings). The name of this theme is saved in the Jekyll `_config.yml` configuration file.

### Support or Contact

Having trouble with Pages? Check out our [documentation](https://help.github.com/categories/github-pages-basics/) or [contact support](https://github.com/contact) and we’ll help you sort it out.
