#	INTEGER SEQUENCE LEARNINIG - CLUSTER VISUALIZATION


## Getting Started

The goal of this project is to develop an AI to predict the next number in a given integer sequence. Unsupervised learning (decision trees) is used to generate clusters in the training data with predefined labels. The test sequence is classified to a cluster leaf node and prediction is made with the data in the leaf node using RNN/search/ heuristics such as mean/median/mode.

This program is a subpart of the project in which decision trees are implemented to split the data and t-SNE is used to visualize the clusters.


### Required libraries

The program is written in python 3.7 and the following libraries are required to run the program

```
numpy
sklearn
scipy
matplotlib
```

###	Required data

The data required to run the program is in "train.csv"

### Installing

The terminal command to install a python libarary names "example" is given below. "example" can be substituted with numpy/sklearn/scipy

```
pip install example

```
###	List of functions

Splitting factors or labels in the decision trees,

```
1. isStatic(): the sequence consists of only 1 number.
2. isIncreasing(): the sequence has an overall increasing tendency.
3. isDecreasing(): the sequence has an overall decreasing tendency.
4. isMonotonic(): the sequence is motononically increasing or decreasing.
5. isOscillating(): the sequence sometimes increases and sometimes decreases.
6. isBinary(): the sequence consists of two states.
7. hasLimitedStates(): the sequence has only a few states compared to its length.
8. isFirstOrder(): each two consecutive numbers of the sequence has the same difference between them.
9. PredictiveMode(): the mode of the sequence appears above a certain threshold.
10. hasGCD(): the numbers in the sequence has a greatest common divisor greater than 1.
11. isNormal(): the numbers in the sequence are normally distributed.
12. hasTrivialLead(): the leading term of the sequence is trivial or has no significance.
13. isSign(): the sequence contains both negative and positive numbers.
14. isComplete(): the sequence contains all the numbers between the minimum and the maximum
of the sequence.
15. hasMeanMode(): the meanand the mode of the sequence are equal.
16. hasIntegerMean(): the mean of the sequence is an integer	

```

Splitting data with decision trees

```
recurse_DTree_binary_split(seqIDArray, featureArray, minLeafSize, assignClusterNumArray)
```

*	recursively split set of sequences into smaller sets according to featureArray and splitDecisionFunc
*	seqIDArray.shape[0] and featureArray.shape[0] is the size of split set
*	seqIDArray identify the location of sequence in the original set
*	featureArray gives the remaining features of sequence that can split


t-SNE cluster visalization

```
ClusterVisulization(seqArray,clusterNumArray,clusterNums,fraction):
```

*	Fraction is the fraction of data you want to show from each cluster
*	clusterNums is the list with cluster names (you can plot the graph for only some clusters to increase visibility)
*	seqArray is the list of sequences
*	clusterNumArray contains integer for each sequence that show which cluster it belongs to.

### Cluster visualization

To get the graph for cluster visualization, the function "ClusterVisulization" has to be called in the code. A sample function call is given below.

```
ClusterVisulization(seqArray,clusterNumArray,clusterNums[:5],1)
```

In the above function call, all the data is used to form the clusters but only first five clusters are visualized

###	References

1.	https://www.kaggle.com/garethjns/classifying-tagging-sequences
2.	https://www.datacamp.com/community/tutorials/introduction-t-sne
3.	https://en.wikipedia.org/wiki/T-distributed_stochastic_neighbor_embedding

