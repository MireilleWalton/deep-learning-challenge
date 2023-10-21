# deep-learning-challenge

MONU-VIRT-DATA-PT-05-2023-U-LOLC-MTTH

# Report

## Overview
This project requires students to develop a binary classifer to predict when applicants will be successful when applying for funding from not-for-profit organisaiton "AlphabetSoup". 

A written analysis on the performance of the model is set out below. 

### Data Preprocessing

Listed below are the columns included in the dataset, separated into 'target', 'features', and 'other'.

#### Target
IS_SUCCESSFUL — Was the money used effectively

#### Features
APPLICATION_TYPE — Alphabet Soup application type
AFFILIATION — Affiliated sector of industry
CLASSIFICATION — Government organisation classification
USE_CASE — Use case for funding
ORGANIZATION — Organisation type
STATUS — Active status
INCOME_AMT — Income classification
SPECIAL_CONSIDERATIONS — Special considerations for application
ASK_AMT — Funding amount requested

#### Other - remove from input data as neither targets nor features
EIN and NAME—Identification columns

## Compile, Traing & Evaluate
The initial model structure included two hidden layers.  The first layer with 80 nodes and the second with 30.  An accuracy score of 72.6% was achieved and a score of 55.6% for loss.    

Three recorded attempts were tried to improve on the model's performance with the aim of achieving an accuracy rather of 75% or better for accuracy.  

#### Attempt 1
The first attempt sought to improve on the initial model by reducing the number of nodes in each layer by 50%, with an imaterial improvement on the initial model - Accuracy 72.9% Loss 55.4%

![image](https://github.com/VioletRogue12/deep-learning-challenge/assets/130148039/c1d18ebd-ebbf-447a-901e-a82465da79c9)

![image](https://github.com/VioletRogue12/deep-learning-challenge/assets/130148039/e4424f43-3b9e-4199-8b4d-590ad8e715a1)


#### Attempt 2
The second attempt futher reduced the number of nodes in layers 1 and 2 down to 20 and 5 respectively and added a third layer which included 10 nodes.  Once again little improvement was achieved in performance with accuracy matching the initial model at 72.6% and loss only marginally lower at 55.2%

![image](https://github.com/VioletRogue12/deep-learning-challenge/assets/130148039/18adfec6-beb0-4cc6-a4db-04ac9ddd1257)

![image](https://github.com/VioletRogue12/deep-learning-challenge/assets/130148039/55729971-7695-40da-9896-de65f87b788f)


#### Attempt 3
The third recorded attempt to improve on the initial models performance by droping additional columns "STATUS", "SPECIAL_CONSIDERATIONS_N", "SPECIAL_CONSIDERATIONS_Y", "ASK_AMT".  Status was removed as it has little influence on sucess of a program. The special considerations columns were removed as these are presumed to be a discretionary 'decision' made by Alphabet whether or not to provide funding and ultimately not related to whether or not what funding was provided equated to the success of a particular program.  "ASK_AMT" was removed as the get.dummies conversation, although resulting in a conversion to an integer did result in a binary conversion returning over 8000 unique values. 

Only two layers were used and nodes increased to 160 and 60 respectively.  This resulted in an accuracy result of 72.9% and loss of 55.9%.

![image](https://github.com/VioletRogue12/deep-learning-challenge/assets/130148039/b449b223-a0da-4caa-bedc-fda244880fe1)

![image](https://github.com/VioletRogue12/deep-learning-challenge/assets/130148039/71c4ca0f-6059-450c-be0e-156576bd28fe)


Many unofficial attempts were made to improve on performance including various iterations of adding subtracting layers and nodes, as well as using kerastuner auto-optimisation.  Tanh was not tested and discarded as it is directional ie values from 1 to -1, rather than 1 adn 0.  None of these attempts were able to achieve any material improvement.



