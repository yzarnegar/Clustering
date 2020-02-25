# Finding more subtypes of non-small cell lung cancer using clustering methods
Exploring the Lung cancer subtypes by clustering the mRNA data
#Question: Are there subtypes of NSCLC other than three known subtypes?

Clustering methods can provide subsets of observations/genes that may reveal some phenotype related subgroups such as cancer subtypes within the data sets. One of the usages of the clustering methods is for DNA microarray data. 

The PAM (partitioning around medoids) algorithm is based on the search for k representative objects or medoids among the observations using dissimilarity values between the objects. After finding a set of k medoids, k clusters will be provided by assigning each observation to the nearest medoid. The aim of PAM is to find k representative objects, in such a way that the sum of dissimilarities of the observations to their closest representative object is minimized. Also, agglomerative Hierarchical clustering was performed based on complete linkage method to build hierarchy of clusters. In agglomerative Hierarchical clustering, each observation is a small cluster including that single observation. Then clusters will keep merging until only one cluster remains with all the observations.


Using mRNA and miRNA data Hierarchical clustering based on complete linkage method and PAM clustering (partitioning around medoids) were performed to see if some new subtypes of non-small cell lung cancer (NSCLC) could be revealed. Regarding the results for mRNA data, it seems that there are more that 3 clusters. Also, regarding plot from PAM object, it seems there are many over laps between 3 clusters so there should be more clusters suggesting existence of some new subtypes of disease besides AC, SCC and LCC. 


<img src="https://user-images.githubusercontent.com/57342758/73779066-fdd07e80-4740-11ea-86d7-cf2d888c7a93.png" width="400" height="400">


<img src="https://user-images.githubusercontent.com/57342758/73779589-cb735100-4741-11ea-937f-9bfc2903c0a3.png" width="400" height="400">

Result from PAM clustering of observations for miRNA data also suggested the posibility of more subtypes for NSCLC. It seems with 5 chosen number of clusters, less overlaps between clusters can be detected.

<img src="https://user-images.githubusercontent.com/57342758/73779537-b8f91780-4741-11ea-8641-5b29a25f438a.png" width="400" height="400">


Hopach Function form “Hopach” package also was used and clusters were produced for miRNA data and the proportion of times a gene belongs to the cluster was calculated. The bootplot function was implemented to provide barplot of the bootstrap reappearance proportions for each gene and each cluster. Following the barplot is provided. 

<img src="https://user-images.githubusercontent.com/57342758/73779672-ed6cd380-4741-11ea-953b-e46cec60f13c.png" width="400" height="400">

Each gene is showed as narrow horizontal bar. If the color of the bar is one color, then the gene is estimated to belong to that cluster otherwise it belongs to more than one cluster. Regarding barplot, it seems there are 3 major cluster of genes probably related to SCC, Ac and LCC but also there are additional clusters of gens suggesting that there should be more subtypes of cancer NSCLC related with those genes. Integration of the mRNA and miRNA data also suggested possibility of new patterns and classes. 

Survival analysis methods were also used to model the survival time to event data. Event was considered as relapse status variable. Subtype SCC was considered as the comparison group. Regarding the following results there is significant difference between sybtype LCC and SCC in terms of survival time. (p-value<0.05).The survival time for SCC was about 2.6 times the survival time for LCC. Also the hazard of the event for subtype LCC is 2.6 times the hazard for SCC. Based on the p-value (0.19) for the log-likelihood ratio test there was not significant difference between our model and null model. 

<img src="https://user-images.githubusercontent.com/57342758/73781115-94526f00-4744-11ea-88f8-8541a0e7d1c8.png" width="600" height="200">


Function pamr.cv from package”pamr” was used to do the 10-fold cross validation for nearest shrunken centroid (PAM) classifier produced by pamr.train function. Another error estimate of the number of misclassifications on the training set is the cross validation error. Subtypes ADEC and SCLC were merged as ADEC-SCLC group. For mRNA data the 10-fold cross validation for PAM are shown following. The cross validation error is really low for AC and it is low for SCC but then it increases and it is high for LCC. For group ADEC-SCLC the misclassification error is high probably there was just 3 observation for this group.

<img src= "https://user-images.githubusercontent.com/57342758/73781353-eeebcb00-4744-11ea-9db9-c2b765c05591.png" width="400" height="400">
