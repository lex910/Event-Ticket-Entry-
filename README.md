# Event-Ticket-Entry-
Using logistic regression to predict if entry into an event will be granted, explores PCA and K means clustering 

## Data Exploration and Visualization
<img width="847" alt="Screenshot 2024-06-19 at 11 25 28 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/7ea6d7d7-f6bc-49c0-b26b-f26e18eab56a">

Summary Statistics: 

<img width="689" alt="Screenshot 2024-06-19 at 11 25 48 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/1a37e652-a996-4e34-8e85-d599a278a36f">

Identifying null values for data cleaning: 

<img width="366" alt="Screenshot 2024-06-19 at 11 26 15 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/3a661b6d-ed42-43de-a254-0dbfb90bfd8d">

Checking for multicollinearity: 

<img width="617" alt="Screenshot 2024-06-19 at 11 26 57 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/e499782b-d453-4d93-b3f5-9d08a6207679">

We can see that none of the variables are highly correlated with eachother so we do not have to worry about any problems with perfect multicollinarity. I will now create histograms to visualize the distribution of all numeric variables.



<img width="795" alt="Screenshot 2024-06-19 at 11 27 47 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/38ae39cf-2fd2-4a95-a7ae-f39d8a36c0e9">
<img width="757" alt="Screenshot 2024-06-19 at 11 28 05 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/1dbced33-ab9d-454e-8bda-b91b7acb3e3a">
<img width="760" alt="Screenshot 2024-06-19 at 11 28 17 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/207c56f5-3712-40f0-8103-c3c7ec55b062">
<img width="750" alt="Screenshot 2024-06-19 at 11 28 27 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/3d077b39-c16f-488a-bf54-695383d31171">
<img width="760" alt="Screenshot 2024-06-19 at 11 28 39 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/b61dc38a-beab-49f9-828e-72fabb9754c9">
<img width="743" alt="Screenshot 2024-06-19 at 11 28 51 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/d8403a36-fca1-4a55-a6cb-6c5a9f64565a">
<img width="793" alt="Screenshot 2024-06-19 at 11 29 03 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/03f0168c-37ab-40e6-8486-3a5bc3c6898c">

We can see that more females were admitted entry compared to men

## Logistic Regression Model 
OOS MSE: 0.27011494252873564
OOS-Accuracy: 0.7298850574712644

## PCA Analysis 
2 dimensions: 

OOS-sample MSE: 0.5172413793103449
OOS-Accuracy: 0.4827586206896552

4 dimensions: 

OOS-sample MSE: 0.3793103448275862
OOS-Accuracy: 0.6206896551724138

6 dimensions: 

OOS-sample MSE: 0.27586206896551724
OOS-Accuracy: 0.7241379310344828

We can see that increasing the number of components increase the accuracy of our model.

## Using lasso 

2 component lasso: 

OOS-Accuracy: 0.5804597701149425

4 component lasso: 

OOS-Accuracy: 0.6206896551724138

6 component lasso: 

OOS-Accuracy: 0.7873563218390804

We can see that using lasso regression results in models of higher accuracy for each different number of components.

## K Means Clustering 
-using age and price columns 

We will choose to make 4 clusters based on the elbow method 

<img width="652" alt="Screenshot 2024-06-19 at 11 35 11 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/4c976194-226e-4765-85ed-060ad49c5830">

Using k-means makes cluster by fitting a mixture model. We need to determine how many clusters to use to seperate our data. Using the elbow method we choose K=4 as the optimal number of clusters. 4 clusters will minimize the sum of squared distances between every point and the centroid of the clusters becasue it is where we see the "elbow" in our graph. It is important to scale the data so that dimensions have equal influence on the cluster assignments. There is no concrete method to determine the optimal K-value, but the elbow method is widly used, but ambiguous and not always reliable.

Number of people assigned to each cluster: 

<img width="100" alt="Screenshot 2024-06-19 at 11 35 57 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/c1542e00-602c-43ef-ad64-67be5297f1bf">


<img width="628" alt="Screenshot 2024-06-19 at 11 36 35 AM" src="https://github.com/lex910/Event-Ticket-Entry-/assets/101606445/ac8192d6-fcf7-4246-841b-715d1723fbc6">
