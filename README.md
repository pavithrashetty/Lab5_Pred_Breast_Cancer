# Predicting Breast Cancer (Lab5_Pred_Breast_Cancer)



####Aim: 
To create machine learning model to predict malignant tumors.
####Technique used:
<p>We are given with data file, contains information about 699 tumors examined and their class as either malignant or not malignant (with additional 11 variables).  This data set is divided as “train data set” and “test data set”. Training set is used to build the model. Test set is used to test the accuracy of the model after it is being built.</p>
<p>Here, main idea is building multiple models with different sample and different initial variables from train data set. It will repeat the process (say) 10 times and then make a final prediction on each observation. This final prediction can simply be the mean of each prediction. Goal is to determine what attributes (or variables) provide the most information that can be used to predict malignancy.</p>
<p> For instance, it will take a random sample of 100 observation and 5 randomly chosen initial variables (for example, clump thickness, uniformity of the cell size, cell shape, marginal adhesion and epithelial cell size) to predict malignant tumors. It will repeat the process with other set of variables and data samples to predict malignancy. This process continues until all data are examined. So, final prediction is a mean of each prediction. Which is more accurate as we consider all possible combination of variables and sample data in the prediction process.</p>
 <p>This is how our model predicts the best possible outcome from the given set of data.</p>
####Success/Failure: 
Our model is tested against “test data set” for accuracy and it is 96% successful in predicting whether the tumor is malignant or benign.
####Performance of the model:
#####Terms used:
<ul>
<li>True positive: Sick people correctly diagnosed as sick.</li>
<li>False positive: Healthy people incorrectly identified as sick.</li>
<li>True negative: Healthy people correctly identified as healthy.</li>
<li>False negative: Sick people incorrectly identified as healthy.</li>
</ul>
<p>Following ROC curve (fig. 1) is created by plotting the ‘true positive rate’ against the ‘false positive rate’ of the model. It is a graphical plot that illustrates the performance of the model. Graph suggests that “true positive rate” is much higher than the “false positive rate”. So, model accuracy is 0.96 (i.e. 96%).</p>

<figure>
  <img src="https://cloud.githubusercontent.com/assets/10646127/6906783/8bfabf1a-d6f6-11e4-8c65-8075b25614cd.png" alt="ROC curve" width="304" height="228">
  <figcaption>Fig 1. ROC curve</figcaption>
</figure>


<p>Positive predictive values (PPV also called Precision) and negative predictive values (NPV) describe the performance of a diagnostic test:</p>
<ul>
<li>Precision (PPV) is calculated as ratio of true positives to all positives: </li>
<ul>
  <li>PPV= True positive / (True positive + False positive)</li>
  <li>This gives people who are actually having cancer out of all the predicted list of people having cancer by the model.</li>
  <li>Our model gives PPV=0.96. High precision relates to a 'low false positive rate'. This confirms that our model returns more relevant results.</li>
</ul>
<li>Recall (True positive rate) is the fraction of relevant instances that are retrieved:</li>
<ul>
  <li>Recall= True positive / (True positive + False negative) </li>
	<li>The percentage of people who are having cancer are correctly identified as having the condition.</li>
  <li>Our model gives recall as 96%. High recall relates to a 'low false negative rate'. This means that model returned most of the relevant results.</li>
</ul>
</ul>


####Variables that are the most important in predicting breast cancer:
Following bar charts (fig 2, fig 3) indicate the importance of the variables in descending order. 

<figure>
  <img src="https://cloud.githubusercontent.com/assets/10646127/6906848/e9b4fe04-d6f6-11e4-8b95-312082d7cb85.png" alt="The Pulpit Rock" width="304" height="228">
  <figcaption>Fig 2. Simple bar chart that shows all of the variables.</figcaption>
</figure>


<figure>
  <img src="https://cloud.githubusercontent.com/assets/10646127/6906854/f100740e-d6f6-11e4-8d9f-9a3d5acec1b0.png" alt="The Pulpit Rock" width="304" height="228">
  <figcaption>Fig 3.  Bar chart that shows the summary of all the variables.</figcaption>
</figure>


* Bare nuclei, normal nucleoli and bland chromatin are signs of benignity. So, they have more importance in determining if a tumor is malignant or benign.
* Uniformity of the cell size / shape: Cancer cells tend to vary in size and shape. That is why these parameters are valuable in determining whether the cells are cancerous or not.
* Epithelial cell size: Epithelial cell that are significantly enlarge may be a malignant cell. So, size of the cell matters.
* Clump thickness: Benign cells are tend to be grouped in monolayers. While cancerous cells are often grouped in multilayers. Therefore clump thickness is one of the important variable.
* Marginal adhesion: Normal cells tend to stick together. Cancer cells tend to lose this ability. So, less adhesion is a sign of malignancy.
* Mitoses: The mitotic activity (how much the tumor cells are dividing) or Mitotic count is an important parameter for the prognosis of breast cancer. However, it is difficult to detect mitosis and make an accurate prognosis. So, it has little less importance than other parameters.

####Drawbacks of the model:
1.	There are chances that model may falsely predict breast cancer. From the precision (0.96) we can interpret that 0.04 of the times model may falsely predict breast cancer.
2.	Model may also miss a malignant case while predicting. From the recall (96%) we can say that 4% of the times model may miss a malignant case.


######Source:
*	http://en.wikipedia.org/wiki/Precision_and_recall
*	https://answers.yahoo.com/question/index?qid=20101204013824AAWTufG







