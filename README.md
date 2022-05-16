# Decision Tree

Implement ID3 algorithm for decision tree using Python

The algorithm is written using OOP and SOLID principles, all the methods in each class perform only one operation which makes it easier for the reader to read and understand the code.
In order to make the report shorter, we have tried to explain all the sections briefly.

## DecisionTreeHelper class
This class defines methods that have been used in various parts of the code, such as calculating entropy, calculating probability, better representing the tree, checking whether the set is a node, and whether this node is the final node.

The methods of this class are called statically in different parts of the code and other classes.

## DecisionTreeTrainer class

This class is used to perform Train operations. This class needs two data to build its object, the first as a string called target_attribute, which represents the title of the column in which our target attribute (the final label) is stored, and the other to The name of the train_dataset that it receives as a Data Frame (which contains the dataset that the algorithm trains on).

## DecisionTreeTester class

This class is written to evaluate the decision tree obtained in the Trainer class (DecisionTreeTrainer) and gives us the accuracy of each tree for different datasets.
The inputs to this class are tree, which is received as a dictionary (the Trainer class and the get () method can be used), target_attribute, which is the same as the Trainer class, test_dataset, which is given as a data frame to the class, and data sets from It is used to evaluate the tree and finally default_label, which is better obtained by voting method on test data, and represents a label that is used in the absence of a path in the tree that is required in the test data. Of course, this argument is not mandatory, and in the absence of None, it is replaced and returns data that the tree has not learned, instead of the maximum number of False values.
(Used if there was a value in the test dataset but it was not learned in the tree.)

## DecisionTreePruning class

This class is used for pruning trees obtained through DecisionTreeTrainer, which uses the Reduced error pruning method according to the task.
The inputs to this class are the trainer, which should be an object of the DecisionTreeTrainer class, and pruning_dataset, which is the validation data used to prune the tree.
There is another argument called threshold, which has a value of 0 by default and indicates the minimum increase in accuracy for pruning a node in a tree in percent.

## DecisionTreeFoldCrossValidation Class

This part of the code belongs to the optional part of the task and is written in order to perform all operations related to the Fold Cross Validation method.
This class has 5 inputs, the last 2 of which have a default value and are optional. The first input of the Train dataset is Validation, which is actually the dataset that we divide into different sections and is introduced as primary_dataset and must be a Data Frame. The second input is test_dataset, which is used to measure the accuracy of the tree and, like the first argument, must be a Data Frame. The third input is target_attribute, which, like the trainer and tester classes, is the title of the column in which the labels are placed. The fourth input represents the number of folds, which is 4 by default. And finally the fifth input, which like the Pruning class is a threshold value that is used to prune each node.
In the following, each step of the homework question is written and the method of using the written classes for each question and the output and related explanations are also included.
