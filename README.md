# PAM_Clustering
Exploring the Lung cancer subtypes by clustering the mRNA data
#Question: Are there subtypes of NSCLC other than three known subtypes?

Clustering methods can provide subsets of observations/genes that may reveal some phenotype related subgroups such as cancer subtypes within the data sets. One of the usages of the clustering methods is for DNA microarray data. 

The PAM (partitioning around medoids) algorithm is based on the search for k representative objects or medoids among the observations using dissimilarity values between the objects. After finding a set of k medoids, k clusters will be provided by assigning each observation to the nearest medoid. The aim of PAM is to find k representative objects, in such a way that the sum of dissimilarities of the observations to their closest representative object is minimized. Also, agglomerative Hierarchical clustering was performed based on complete linkage method to build hierarchy of clusters. In agglomerative Hierarchical clustering, each observation is a small cluster including that single observation. Then clusters will keep merging until only one cluster remains with all the observations.


Using mRNA and miRNA data Hierarchical clustering based on complete linkage method and PAM clustering (partitioning around medoids) were performed to see if some new subtypes of non-small cell lung cancer (NSCLC) could be revealed. Regarding the results for mRNA data, it seems that there are more that 3 clusters. Also, regarding plot from PAM object, it seems there are many over laps between 3 clusters so there should be more clusters suggesting existence of some new subtypes of disease besides AC, SCC and LCC. 

![image](https://user-images.githubusercontent.com/57342758/73779066-fdd07e80-4740-11ea-86d7-cf2d888c7a93.png)


![image](https://user-images.githubusercontent.com/57342758/73779085-0923aa00-4741-11ea-9920-f3b764d6ba40.png)




Regarding the plot from PAM object, it seems there are many over laps for 3 clusters situation. So probably there should be other subtypes of NSCLC besides SCC, LCC and AC addressed by some of the genes. It seems with 5 chosen number of clusters, less overlaps between clusters can be detected. 



Hopach Function form “Hopach” package also was used and clusters were produced for miRNA data and the proportion of times a gene belongs to the cluster was calculated. The bootplot function was implemented to provide barplot of the bootstrap reappearance proportions for each gene and each cluster. Following the barplot is provided. 




Each gene is showed as narrow horizontal bar. If the color of the bar is one color, then the gene is estimated to belong to that cluster otherwise it belongs to more than one cluster. Regarding barplot, it seems there are 3 major cluster of genes probably related to SCC, Ac and LCC but also there are additional clusters of gens suggesting that there should be more subtypes of cancer NSCLC related with those genes. 

![image](https://user-images.githubusercontent.com/57342758/73778670-6a974900-4740-11ea-8b37-23ea77e52049.png)
