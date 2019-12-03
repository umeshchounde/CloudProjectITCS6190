## Title: Human Activity Recognition using Smartphone and Smartwatch Sensor Data

Project Group:
Umesh Chounde	801075505
Jitesh Golatkar	801073392

4.Today there are billions of people carrying smart devices such as smartphones, fitness gadgets, smartwatches. These sensor-rich gadgets generates larger amount of data that can be utilized using machine learning techniques and big data techniques for mining and deriving meaningful insights about human activity. Some of the common applications that are widely used are fitness trackers, and personal assistant systems for dissabled people. In this project we will use such large dataset and process it using distributed computing frameworks like Spark as well as use one of the classification algorithms in machine learning to recognise human activity like walking, jogging etc.

5.WISDM dataset consist of raw accelerometer and gyroscope data collected from smartphones and smartwatches. This data is collected from 51 individuals who were assigned to execute 18 different tasks for 3 minutes. Each individual was had smartwatch and smartphone placed on them. There are total 15630426 instances consisting of 6 attributes (subject_id, activity, timestamp, x-reading, y-reading, z-reading). This is a labelled dataset, thus is suitable for classification tasks.

DataSet: WISDM Smartphone and Smartwatch Activity and Biometrics Dataset Data Set
[DataSetLink](http://archive.ics.uci.edu/ml/datasets/WISDM+Smartphone+and+Smartwatch+Activity+and+Biometrics+Dataset+)

Feature Selection and Data Preparation:
    We vizualised small set of data for each activity such as walking and jogging we came to know that accelaration of x, y, z axis plays an important role in differentiating the activities.
    
Average acceleration:    
   We calculated average accelaration for each axis of the record
Variance:
   We calculated variance of accelaration for each axis of the record
Average absolute difference:
   We calculated average absolute differencee of accelaration for each axis of the record
Average resultant acceleration (1/n * sum [√(x² + y² + z²)])
Average time between peaks (max) (Y-axis)




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
