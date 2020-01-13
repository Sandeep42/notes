# Making Better Mistakes: Leveraging Class Hierarchies with Deep Networks

[https://arxiv.org/abs/1912.09393](https://arxiv.org/abs/1912.09393)

* How to avoid making catastrophic mistakes while predicting?
* While ImageNet top-1 accuracy has been increasing overtime, the severity of the mistakes measured by LCA distance (least common ancestor) signifying how far off the prediction is from the hierarchy was unchanged. This means although we are making lesser mistakes than the usual, we are still making mistakes that are costly. How to approach this problem?
* Three traditional methods exist.
	* Label Embedding: The labels are embedded into some space where their relations are preserved. This enables us to add an additional term in the loss function that penalises if the predicted label is very far off from the original label.
		* You can potentially embed the hierarchy of the labels and use a distance measure to penalise the loss function.
	*  Hierarchical losses: In these methods, the loss function itself is modified to fit with the class hierarchy of the labels. You take the LCA distance between the classes and optimise directly into the loss function.
	*  Hierarchical architectures: `The core idea is to “divide and conquer” at the structural level, with the classifier assigning inputs to superclasses at earlier layers and making finegrained distinctions at later ones.`
* This paper proposes two methods:
	* Hierarchical crossentropy: Uses conditional probabilities on the hierarchical tree as weights on the loss function. The weights are parametrised with an exponential function. Refer to the paper for full math.
	* Soft labels: The soft labels approach uses a label embedding method where they embed classes in such a way that near (in terms of LCA distance) are embedded closer. Much similar to Word2Vec, just a different distance metric and comparison function.
* Paper uses two datasets, and shows the trade off between accuracy and severity of the mistakes.
* Can you use arbitrary hierarchies? No, the performance drops when you do so. So, the network is able to learn only when the hierarchies are related in some context. Otherwise, it doesn't help much.
* You need to have the hierarchy though. Typically, it should be easy enough to find since the number of classes is less. Otherwise, one use external clustering approaches.