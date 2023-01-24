Practical Assignment 3. Bank campaign response.

Using the hisotircal performance data from over 2 years of running various marketing campaigns, we were able to build a machine learning classifier model that helps identify top likely candidates with highest probability to respond to the campaign.

While no single characteristic was able consistently predict likelyhood to respond (see correlation matrix below), having no credit in default, student and retired statuses have highest positive correlation w/ likelihood to accept the offer.
<img width="639" alt="image" src="https://user-images.githubusercontent.com/63613300/214190655-c11a2ce0-2f61-43cc-9dc5-77c2f9b217d8.png">

Given the imbalance of classes (over 80% of customers do NOT accept the offer), we choose AUC as the north start for model optimization (there is no strong preference for type I / type II error avoidance given the business problem at hand). After running multiple different models (KNN, Logistic Regression, Decision Tree, etc.), the model with optimal AUC on test data ended up being KNN. 

<img width="467" alt="image" src="https://user-images.githubusercontent.com/63613300/214191380-3986a975-3e06-4a4f-8249-6f89220da8d1.png">

Adjusting the classifier probability to account for class imbalance, we end up with the following confusion matrix:

<img width="254" alt="image" src="https://user-images.githubusercontent.com/63613300/214191488-eb399542-bdf7-4bc1-8067-76728d41f7b8.png">

Overall, as a result of the current model, we are able to capture roughtly 2/3rds of all likely acceptors while contacting just 50% of the original population. This will allow to focus resources on most likely converts without significantly affecting revenue.

As next steps, we recommend
- deploying the model to free up call center resources and focus on most likely converts
- explore adding extra profile-level data where possible (i.e. 3rd party sources) to further improve accuracy
- test out different offers via a randomized experiment - it's possible some customers are more responsive to certain campaigns than others

