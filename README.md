# Network Traffic Classification for Inferring Network Behavior #

<div style="text-align: justify">
We present our work for the track of “Case studies demonstrating (dis)advantages of choosing AI/ML techniques for networking over more traditional ones”. This research work, the focus is on comparative analysis on classical ml models and neural models, in its ability to infer known network behavior from the payload independent communication patterns observed as statistical characteristics over a window time, by building a supervised learning multi class classifier. We carry out our experiments using NIMS data trace, a publically available network dataset, which has been widely used to build network models. Our premise of research is to build machine learning models using all known available traditional techniques, which include statistics, classic machine learning algorithms and neural networks too. This premise of this research exploration is to present the importance of each learning paradigm and see how we can how we can leverage all of them and benefit overall, than choosing one versus another. Such a premise will lead us to think in terms of different way an augmented solution can be built.

## Decision trees ##
We have used _J48_ trees in our experiments. It is an open source Java implementation of the _C4.5_ algorithm in the Weka data mining tool.

#### Algorithm ####

C4.5 builds decision trees from a set of training data using the concept of information entropy. The training data is a set of already classified samples. Each sample consists of a vector which contains features of the sample, as well as the class in which the sample falls. At each node of the tree, C4.5 chooses the attribute of the data that most effectively splits its set of samples into subsets enriched in one class or the other. The splitting criterion is the normalized information gain (difference in entropy). The attribute with the highest normalized information gain is chosen to make the decision. The C4.5 algorithm then recurses on the partitioned sublists.

<!-- This algorithm has a few base cases
* All the samples in the list belong to the same class. When this happens, it simply creates a leaf node for the decision tree saying to choose that class
* None of the features provide any information gain. In this case, C4.5 creates a decision node higher up the tree using the expected value of the class
* Instance of previously-unseen class encountered. Again, C4.5 creates a decision node higher up the tree using the expected value

#### Pseudocode

```java
    Check for base cases
    For Each attribute 'x':
        Find the normalized information gain ratio from splitting on 'x'
    Let 'x_best' be the attribute with the highest normalized information gain
    Create a decision node that splits on 'x_best'
    Recurse on the sublists obtained by splitting on 'x_best', and add those nodes as childrenof node.
``` -->

#### Advantages
1. Simple to understand and interpret
2. Important insights can be generated
3. Help determine worst, best and expected values for different scenarios
4. Use a white box model
5. Can be combined with other decision techniques

#### Disadvantages
1. They are unstable, a small change in data can lead to a large change in the structure of the optimal decision tree
2. They are often relatively inaccurate but random forests of multiple decision trees can give better results
3. Calculations can get very complex, particularly if many values are uncertain and/or if many outcomes are linked



</div>