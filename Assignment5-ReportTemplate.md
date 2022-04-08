**SENG 438- Software Testing, Reliability, and Quality**

**Lab. Report \#5 – Software Reliability Assessment**

| Group \#: 23         |   |
|-----------------  |---|
| Manpreet Singh    |   |
| Tianfan Zhou      |   |
| Girimer Singh     |   |
| Muhammad Shakeel  |   |

# Introduction
The goal of this lab was to analyze the integration test data using the reliability assessments tools. The assessment of the failure data was done by Reliability growth Testing using C-SFRAT and Reliability assessment using a Reliability demonstration chart. After analyzing failure data from both techniques, the results computed from the techniques were compared. Moreover, the advantages and disadvantages of both techniques were discussed, and also similarities and differences between them.

# Assessment Using Reliability Growth Testing 
C-SFRAT tool was used for reliability growth testing. This tool allowed us to apply multiple models to the failure data to evaluate accuracy of each model. 

## Result of model comparison (selecting top two models)
There are a total 8 models available in tool with each up to 6 combinations of covariates. Two best fit models were identified based on highest mean and median weighted from multiple goodness of fitness methods. As shown in below figure 1, top two models were Discrete Weibull (Type III) with covariate F and IFR generalized Salvia & Bolin with covariate F.
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/10.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 1- Model comparison
</p>
</br>
</br>

## Result of range analysis (an explanation of which part of data is good for proceeding with the analysis)
Intensity of failure at interval 2 is very high as shown in figure 2. Removing interval 1 and 2 make the slightly more accurate than before and is illustrated in figure 3.
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/11.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 2- Failure intensity - including interval 1 and 2
</p>
</br>
</br>

<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/12.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 3- Failure intensity – excluding interval 1 and 2

</p>
</br>
</br>

## Plots for failure rate and reliability of the SUT for the test data provided 
 
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/13.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 4-  Failure rate

</p>
</br>
</br>
Prediction from DW3 for next 40 intervals show failure rate to be relatively lower as illustrated in figure 5. System is becoming more reliable.
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/14.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 5-  Failure prediction using DW3 model

</p>
</br>
</br>

## A discussion on decision making given a targe failure rate
Based on the prediction, it is reasonable to achieve the target failure rate of 0.55. Target failure rate can be possible reached in 12 more intervals.

<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/15.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 6-  Target failure rate

</p>
</br>
</br>

Target failure rate would impact the testing of the system. If the target failure rate is lower, then more testing would be required and performed for the system. Similarly, if the target rate is higher, then less testing would required for the system. Utimately, the target rate would impact the allocation of resources that are allotted to the system.


## A discussion on the advantages and disadvantages of reliability growth analysis 
There are a lot of benefits of the Reliability Growth Analysis and some of them are as follows

1. It helps to enhance the reliability of the system and thus also helps the system to reach the reliability goal.
2. This technique provides a way to deliver the product faster to the software market.
3. Using this technique, product development costs can be reduced since, with this technique, project planning is implemented.

There are some disadvantages of the reliability growth analysis and some of them are mentioned below

1. In order to accurately implement this technique, it requires a lot of resources.
2. This technique is time-consuming.

# Assessment Using Reliability Demonstration Chart 
The risk parameters can determine the probability of an error in the estimate. As shown within figure 7, the parameters we used for testing are 2.0 for Discrimination Ratio γ, 0.1 for Developer’s risk a, and 0.1 for user’s risk b, where developers risk is rejecting an acceptable system and user’s risk is releasing an unacceptable system. These 3 risk parameters together determine the acceptance (green), rejection (red), and continue (yellow) segment areas on RDC, which helps us to judge the reliability of the system.
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/1.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 7- Risk Profile Paramteres
</p>
</br>
</br>
The input of the RDC is the cumulative failures count and cumulative execution time of the system. We choose an hour as the unit of the input event. The cumulative failure counts and execution time is taken from the failure data csv file provided with the assignment 5 repository. The 16 observation data records are taken from T=10 to T=26 are illustrated in figure 8. In our test, we set our initial maximum acceptable number of failures value (target MTTF)  to 2.1. Based on that initial value, we did an experiment to test it with twice and half of that value to reassess the system. One thing to notice in figure 8 is that based on the limitation of the RDC-11 analysis tool (y-axis can show a maximum of 16 failures), we use 0.1x original failure count and 0.1x maximum acceptable number of failures value to let the plotting can be correctly displayed on the graph.
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/9.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 8- Failure Count and Time Data for the Graphs
</p>
</br>
</br>
As can be seen on the first graph in figure 9, when we choose to have a maximum acceptable number of failures as 2.1, the observed failures line is located within the continued test area and touches the acceptable green area. 
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/6.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 9- Plot for MTTFmin
</p>
</br>
</br>
For the second graph in figure 10, if we choose to decrease the maximum acceptable number of failures from 2.1 to 1.05 (half), the observed failures line is located within the continued test area. This is to say, based on the collected data information we have, we cannot make any accept or reject conclusions about the system. More failure tests need to be done for the system. So that we actually need to be provided more data to make a decision.
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/7.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 10- Plot for half of the MTTFmin
</p>
</br>
</br>
For the third graph in figure 11, if we choose to decrease the maximum acceptable number of failures to less than half of the MTTFmin which is 0.075, the observed failures line will reach the reject area. Based on the existing system failure data we have, we need to reject the system if we are only willing to accept a maximum of 0.75 failures per hour on running the system. There is a 5% chance that this reject decision is accidentally wrong (because of the 0.05 developer's risk).
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/4.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 11- Plot for value less than half of the MTTFmin
</p>
</br>
</br>
For the fourth graph in figure 12, if we choose to increase the maximum acceptable number of failures from 2.1 to 4.2 (double), the observed failures line will reach the acceptance area. Based on the existing system failure data we have, we can accept the system if we are willing to accept a maximum of 4.2 failures per hour on running the system. Also, there is a 5% chance that this acceptance decision is accidentally wrong (because of the 0.05 user’s risk).
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/8.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 12- Plot for double of the MTTFmin
</p>
</br>
</br>

## Explain your evaluation and justification of how you decide MTTFmin
The minimum MTTF value we got from the data we selected is 2.1. As can be seen on the graph in figure 3, when the MTTF (maximum acceptable number of failures) value is 2.1, the failure line barely reached the acceptance area. This is to say, if we choose an MTTF value smaller than 2.1, the line will still be located within the continued area. And if we choose any value which is greater than 2.1, more parts of the line will reach the acceptance area. So 2.1 is the minimum MTTF value, which means if we want to accept the system, we must accept the failure rate of at least 2.1 failures per hour.

## A discussion on the advantages and disadvantages of RDC
Advantages:
1. It is a time and cost-effective solution to understand the reliability of a system 
2. Open source and can be viewed and accessed by anyone
3. A useful technique to see whether more testing is required so that reliability of a system can be increased 

Disadvantages:
1. The exact quantitative value of reliability cannot be calculated
2. Experimenting with MTTF or the what-if scenarios could potentially waste time  
3. The RDC can demonstrate only the trend of changes 


# Comparison of Results
From the result of reliability demonstration chart testing, we conclude that we can accept the system if we are willing to accept the maximum failure rate of 2.1 failures per hour. Any failure  rate greater than 2.1 will cause a rejection. And from the result of the reliability growth testing, we conclude that the reasonable maximum failure rate to accept the system is 0.55, which means we can not have more than 1 error within a 2 hours period in order to accept the system. As can be seen from results, reliability growth testing gives a relatively lower value of failure rate for acceptance situations in our testing. However, the result given by RDC can tolerate slightly more errors. This result depends on our minimal tolerance  of error. And if we can try to keep the failure rate of the system at a value lower than 0.55, both testing methods will give an acceptance result, so that we can have more confidence to make the acceptance decision with the system we are testing.

# Discussion on Similarity and Differences of the Two Techniques
The Reliability Growth Testing and the Reliability assessment using the RDC are both used for analyzing the failure data of the system and for understanding the reliability of the system. The Reliability Growth Testing is based on failure times or failure count and MTTF while the Reliability Demonstration Chart is based on failure times and the MTTF. The Reliability Growth uses mathematical model when it gets tested, and faults are removed. Using the Reliability Growth Testing, the failure data can be analyzed and displayed as the time between the failures graph and failure intensity graphs. So, these graphs can help us to visualize the entire data over the entire time range. Whereas, in Reliability Demonstration Chart, it is used for checking whether the target failure rate or MTTF is met by the system based on the given failure data of the system. In RDC, the failure data is compared and analyzed with the accepting and rejecting conditions.

# How the team work/effort was divided and managed
We worked together to download all the related software or programs needed to complete the lab successfully. For part 1, the program called C-SFRAT was used. For part 2, Reliability-Demonstration-Chart.xls and its manual RDC-xls-Overview.pdf were used. The work was divided evenly among all group members. Grimier and Muhammad worked on part 1 while Manpreet and Tianfan worked on part 2. Our results and findings were compared with each other and verified to make sure that our results were correct. Once our results were verified among each other then we worked on completing the report. 

# Difficulties encountered, challenges overcome, and lessons learned
This lab gave us a good understanding of becoming familiar with reliability growth assessment tool tools like C-SFRAT and how they can be used to create graphs of the failure rate. The second part of this lab used the Reliability Demonstration Chart (RDC) to check if the MTTF is met or not. Since there were some data points given and this was used to see the trend for the reliability of the system. Some of the difficulties that we faced were related to part 1 as the SRTAT tool was unresponsive and outdated compared to modern testing tools as it was designed on older Windows versions. The Graphic User Interface (GUI) was very hard to see the display of the window and results. 

# Comments/feedback on the lab itself
By completing this lab, we have learned how reliability assessment tools can be used to investigate failure data using the following techniques: Reliability growth testing and Reliability assessment using the Reliability Demonstration Chart (RDC). However, downloading these tools did waste a lot of our time and this time could have been used to complete the lab or to further enhance our understanding of these topics. Also, some tools such as the STRAT was not working as they should be and this caused frustration.  Furthermore, the instructions given in the lab manual were very vague in terms of modeling data using these tools. 
