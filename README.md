##Fault detection and classification using ANN







**Table of Contents**

[TOCM]

[TOC]

##Overview
This is a simple project based on classification of the faults in electrical power systems using artificial neural networks. The voltages of three phases are taken as input and  the model predicts the phase(s) having fault .

##Motivation
The idea is  to combine the concepts of  electrical power systems and machine learning into one. It is known that electrical systems are complex and the elements  are dynamic , hence  in case of a fault , it is important for grids and electricity generating plants to detect them early and get back into the  stable condition.

##Requirements

    MATLAB R2019
    SIMULINK
	DEEP LEARNING TOOLBOX







##Technical Aspect

    Data Preparation
    Training the model and tuning it for the optimum hyperparameter
    Training the model for the hyperparameter and deployment.
	Results

###Data preparation
-Simulated a three phase power system using blocks from Simulink and analysed the faults for different voltage values .

![power_system_simulation](https://user-images.githubusercontent.com/73178941/96730512-db1bee00-13d3-11eb-8655-a8c9f47a86af.PNG)


**Simulation of faults **


A-G FAULT (Fault between Phase A and ground)

![iag](https://user-images.githubusercontent.com/73178941/96731693-28e52600-13d5-11eb-9a1d-b6a672d531db.PNG)

B-G FAULT (Fault between Phase B and ground)


![ibg](https://user-images.githubusercontent.com/73178941/96731697-2b478000-13d5-11eb-8900-853b0ba9fbd6.PNG)

C-G FAULT (Fault between Phase C and ground)


![icg](https://user-images.githubusercontent.com/73178941/96731712-2e427080-13d5-11eb-9a64-afeb914ee8c4.PNG)



A-B FAULT (Fault between Phase A and B)


![I_AB](https://user-images.githubusercontent.com/73178941/96731761-3d292300-13d5-11eb-8c9f-979046a0e2aa.PNG)

B-C FAULT (Fault between Phase B and C)



![I_bc](https://user-images.githubusercontent.com/73178941/96731773-40241380-13d5-11eb-9536-87fe80ca966e.PNG)

A-C FAULT (Fault between Phase A and C)



![Iac](https://user-images.githubusercontent.com/73178941/96731797-474b2180-13d5-11eb-8055-7b7b78cb77e5.PNG)


B-C-G FAULT



![I_BCG](https://user-images.githubusercontent.com/73178941/96732004-82e5eb80-13d5-11eb-86d2-3a75e1b2e8ec.PNG)

A-C-G FAULT 



![I_acg](https://user-images.githubusercontent.com/73178941/96732023-87aa9f80-13d5-11eb-878d-4a47d249f5c0.PNG)



A-B-C-G FAULT




![I_abcg](https://user-images.githubusercontent.com/73178941/96732050-8da08080-13d5-11eb-82a9-7c7e637be87b.PNG)



NO FAULT


![No_fault](https://user-images.githubusercontent.com/73178941/96732065-91cc9e00-13d5-11eb-869d-479d260d7676.PNG)






After combining the values of voltages and currents , a csv file is prepared which contains voltages of the three phases and a boolean value for each of the phases ( A,B,C,G)  as  1 for occurence of fault  and 0 for non-occurence. 

### Training the model and tuning it for the optimum hyperparameter


The dataset is divided into training , validation and test set in the ratio 
[60% ,30%, 10%].
  The  model is trained on a  random value of hyperparameter initially just to get a feel of the neural network . Then, it is tuned for the best hyperparameter by iterating it through a range and finding the best hyperparameter which gives the minimum error on the validation set.

Plot of the rmse of the training , validation and test set


![plot](https://user-images.githubusercontent.com/73178941/96734671-67c8ab00-13d8-11eb-98d1-af08fd816c1b.PNG)


A MAGNIFIED PLOT  OF THE VALIDATION SET RMSE 

![best_hyperparam](https://user-images.githubusercontent.com/73178941/96734980-b24a2780-13d8-11eb-92a8-cd9c453f97fb.PNG)


Thus , we find that at X=38 (NO. OF HIDDEN LAYERS ) , we get the minimum rmse for the validation set.




###Training the model for the hyperparameter and deployment.

The neural network is trained for the optimum hyperparameter.






![Capture1](https://user-images.githubusercontent.com/73178941/96735407-2c7aac00-13d9-11eb-99b3-f95756bec266.PNG)



###Results

![Capture2](https://user-images.githubusercontent.com/73178941/96735918-ae6ad500-13d9-11eb-9f51-b5f33f5a4c28.PNG)

The overall mean square error of the trained neural network is 0.04961.

![Capture5](https://user-images.githubusercontent.com/73178941/96735928-b165c580-13d9-11eb-8ce5-14203e4456ae.PNG)



The correlation coefficient was found to be 0.86068 which indicates satisfactory correlation between the targets and the outputs.


![Capture4](https://user-images.githubusercontent.com/73178941/96735952-b75ba680-13d9-11eb-8072-6419121037a4.PNG)






##Conclusion

1.Artificial neural networks are a reliable and effective method for an electrical power system fault classification.
2.Since we have a large training data set , ANN with back propogation is used as it gives good performance in such data heavy systems.







