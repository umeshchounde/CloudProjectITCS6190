# 1.**Title: Human Activity Recognition using Smartphone and Smartwatch Sensor Data**

## 2. **Project Group:**

Umesh Chounde

Jitesh Golatkar

## 4. **Project Motivation**

Today there are billions of people carrying smart devices such as smartphones, fitness gadgets, smartwatches. These sensor-rich gadgets generates larger amount of data that can be utilized using machine learning techniques and big data techniques for mining and deriving meaningful insights about human activity. Some of the common applications that are widely used are fitness trackers, and personal assistant systems for dissabled people. We personally used such devices for tracking the activities. We felt that it would be interesting to know how it classify activities and we decided to implement the classification algorithm we studied in this course.

## 3. **Dataset Information**
In this project we are using such large dataset and process it using distributed computing frameworks like Spark. We are using couple of the classification algorithms in machine learning to recognise human activity like walking, jogging etc.

5.WISDM dataset consist of raw accelerometer and gyroscope data collected from smartphones and smartwatches. This data is collected from 51 individuals who were assigned to execute 18 different tasks for 3 minutes. Each individual was had smartwatch and smartphone placed on them. There are total 15630426 instances consisting of 6 attributes (subject_id, activity, timestamp, x-reading, y-reading, z-reading). This is a labelled dataset, thus is suitable for classification tasks.

DataSet: 
WISDM Smartphone and Smartwatch Activity and Biometrics Dataset
[DataSetLink](http://archive.ics.uci.edu/ml/datasets/WISDM+Smartphone+and+Smartwatch+Activity+and+Biometrics+Dataset+)

The accelerometer form devices measures the accelaration in 3 dimessions, along with x axis, y axis and z axis. 
X axis accelaration describes horizontal movement body. 
Y axis accelaration describes upward and downward movement of body. 
Z axis accelaration describes forward movement of body.

## **Feature Selection and Data Preparation:**

   We vizualised small set of data for each activity such as walking and jogging we came to know that accelaration of x, y, z axis plays an important role in differentiating the activities. We also considered peak values of accelarations that can help us differentiate activity, beacause jogging will be having most peak accelaration compared to walking and other activities. In the case of climbing up and down of stairs have periodic actions and we can detect those activities on the basis of activity periodicity. In case of normal activity such as sitting we get constant accelaration for long period.  After thorough study and research we came up with following features might be helpful for building a model. The given data is already sorted according to activity and timestamp of each activity.
    
### **Average acceleration:**

Each activity data records are divided in batches of 200 records. We calculated average accelaration for each axis of the record
   
### **Variance:**

Each activity data records are divided in batches of 200 records. We calculated variance of accelaration for each axis of the record
   
### **Average absolute difference:**

We calculated average accelaration for each axis and took absolute difference with average accelaration. Average of this absolute difference is calculated again.
   
### **Average resultant acceleration:**

Average resultant is calculated using the formula.(1/n * sum [√(x² + y² + z²)])
   
### **Average time between peaks **

Initially we calculated global maxima for each axis accelaration. Selected all the other local maximum who has value more than 90% of global maxima. Then average of all such values are taken.


## 6. **Algorithms**

### Decision Tree

Initially we used Decision Tree for classifiaction of the activities.

### Naive Bayes Classification 

## 8,9.**Results and Performance evaluation**

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
