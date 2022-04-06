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
## A discussion on the advantages and disadvantages of reliability growth analysis 
There are a lot of benefits of the Reliability Growth Analysis and some of them are as follows

1. It helps to enhance the reliability of the system and thus also helps the system to reach the reliability goal.
2. This technique provides a way to deliver the product faster to the software market.
3. Using this technique, product development costs can be reduced since, with this technique, project planning is implemented.

There are some disadvantages of the reliability growth analysis and some of them are mentioned below

1. In order to accurately implement this technique, it requires a lot of resources.
2. This technique is time-consuming.

# Assessment Using Reliability Demonstration Chart 
The risk parameters can determine the probability of an error in the estimate. As shown within figure 1, the parameters we used for testing are 2.0 for Discrimination Ratio γ, 0.05 for Developer’s risk a, and 0.05 for user’s risk b, where developers risk is rejecting an acceptable system and user’s risk is releasing an unacceptable system. These 3 risk parameters together determine the acceptance (green), rejection (red), and continue (yellow) segment areas on RDC, which helps us to judge the reliability of the system.
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/1.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 1- Risk Profile Paramteres
</p>
</br>
</br>
The input of the RDC is the cumulative failures count and cumulative execution time of the system. We choose an hour as the unit of the input event. The cumulative failure counts and execution time is taken from the failure data csv file provided with the assignment 5 repository. The 16 observation data records are taken from T=10 to T=26 are illustrated in figure 2. In our test, we set our initial maximum acceptable number of failures value (target MTTF)  to 1.5. Based on that initial value, we did an experiment to test it with twice and half of that value to reassess the system. One thing to notice in figure 2 is that based on the limitation of the RDC-11 analysis tool (y-axis can show a maximum of 16 failures), we use 0.1x original failure count and 0.1x maximum acceptable number of failures value to let the plotting can be correctly displayed on the graph.
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/2.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 2- Failure Count and Time Data for the Graphs
</p>
</br>
</br>
As can be seen on the first graph in figure 3, when we choose to have a maximum acceptable number of failures as 2.1, the observed failures line is located within the continued test area and touches the acceptable green area. This is to say, based on the collected data information we have, we cannot make any accept or reject conclusions about the system. More failure tests need to be done for the system. So that we actually need to be provided more data to make a decision.
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/6.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 3- Plot for MTTFmin
</p>
</br>
</br>
For the second graph in figure 4, if we choose to decrease the maximum acceptable number of failures from 2.1 to 1.05 (half), the observed failures line is located within the continued test area. This is to say, based on the collected data information we have, we cannot make any accept or reject conclusions about the system. More failure tests need to be done for the system. So that we actually need to be provided more data to make a decision.
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/7.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 4- Plot for half of the MTTFmin
</p>
</br>
</br>
For the third graph in figure 5, if we choose to decrease the maximum acceptable number of failures to less than half of the MTTFmin which is 0.075, the observed failures line will reach the reject area. Based on the existing system failure data we have, we need to reject the system if we are only willing to accept a maximum of 0.75 failures per hour on running the system. There is a 5% chance that this reject decision is accidentally wrong (because of the 0.05 developer's risk).
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/4.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 4- Plot for value less than half of the MTTFmin
</p>
</br>
</br>
For the fourth graph in figure 6, if we choose to increase the maximum acceptable number of failures from 2.1 to 4 (double), the observed failures line will reach the acceptance area. Based on the existing system failure data we have, we can accept the system if we are willing to accept a maximum of 3 failures per hour on running the system. Also, there is a 5% chance that this acceptance decision is accidentally wrong (because of the 0.05 user’s risk).
<p align="center">
  <img width="600" src="https://github.com/seng438-winter-2022/seng438-a5-tiz00013/blob/main/images/8.png" alt="Material Bread logo">
</p>
<p align="center">
   Figure 6- Plot for double of the MTTFmin
</p>
</br>
</br>

## Explain your evaluation and justification of how you decide MTTFmin
The minimum MTTF value we got from the data we selected is 2.1. As can be seen on the graph in figure 3, when the MTTF (maximum acceptable number of failures) value is 2.1, the failure line barely reached the acceptance area. This is to say, if we choose an MTTF value smaller than 2.1, the line will still be located within the continued area. And if we choose any value which is greater than 2.1, more parts of the line will reach the acceptance area. So 2.1 is the minimum MTTF value, which means if we want to accept the system, we must accept the failure rate of at least 2.1 failures per hour.

# Comparison of Results

# Discussion on Similarity and Differences of the Two Techniques

# How the team work/effort was divided and managed

# 

# Difficulties encountered, challenges overcome, and lessons learned

# Comments/feedback on the lab itself
