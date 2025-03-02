# This repository contains Penguins Cluster using K-Means Clustering

# Description
The dataset is downloaded at kaggle in this link https://www.kaggle.com/datasets/youssefaboelwafa/clustering-penguins-species
which have these column : 
1. culmen_length_mm: culmen length (mm)
2. culmen_depth_mm: culmen depth (mm)
3. flipper_length_mm: flipper length (mm)
4. body_mass_g: body mass (g)
5. sex: penguin sex

# How i started
I was seeking for dataset for learn unsupervised then i found this cute penguins dataset... after i download it
i destroy the dataset hehe.. i did that ofc to make me clean the data first then i can cluster them
1. Data Check :
   After i checked all the data types, and change the sex colomns to NaN (we need to change it to number)
   i check the null at every colomn, i use isna and sum to sum the is null and i got 8
2. Check the outliers :
   I did it by using Boxplot, the value has outlier then i solved it using IQR so i can got the lower and
   upper bound. After i got the IQR then do winsorizing which mean apply on dataset
   ![Image](https://github.com/user-attachments/assets/c07a8e80-6f46-4697-8722-6cff95ac3d1c)
4. Normalize :
   Yea ofc because the data number have huge value so it can make unbalanced when it comes to clustering, so
   i normalize it using standard scaler
5. Finding Cluster :
   By using KMeans i start from 1 to 10 cluster to see the differences, the graph get down so hard when
   it comes to 2 but also 2 to 3 and 4 to 5 are questionable, so i move to use Silhoutte Score Method to
   find the perfect cluster number
   ![Image](https://github.com/user-attachments/assets/c72d7d01-9542-4fc2-a960-2eee8bc69b7f)
   ![Image](https://github.com/user-attachments/assets/8acab6e9-50bd-466e-bf2f-d3973ba0c02d)
6. Clustering :
   In the end i clustered it by 2 cluster
   ![Image](https://github.com/user-attachments/assets/634954f9-ab0e-4201-adb1-cb391ead3503)
7. Evaluation : I use davies bouldin, calinski and shilhoutte score to evaluate every cluster number
   (just to make sure that the true cluster is 2)
8. Histplot by gender and population: Then we can analyze every cluster. from graph we can conclude that cluster number 0 has more
   penguins species than the number 1
   ![Image](https://github.com/user-attachments/assets/49303bc4-2f0e-4bf3-aaf1-75f7f0a57ebd)
9. Histplot by body mass :
    from histplot i can conclude that cluster number 0 has the highest population of 3500 - 4000 body mass in g, meanwhile its decresed and fully stop when reaching 5kg
    and cluster number 1 has the highest in population with body mass in g in maybe from 4700 - 5000 and it slowly decreased until 6000 g
    ![Image](https://github.com/user-attachments/assets/f0971834-d210-4ce1-abc4-6232402b251c)

# Summary
We can conclude that Cluster 0 has much penguins also the average of body mass is under 4000 g, but on the other
side we can see that cluster 1 has a few penguins and the most of it has 4500 - 5000 body mass in g
