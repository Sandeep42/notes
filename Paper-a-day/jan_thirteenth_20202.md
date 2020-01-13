
# Robust breast cancer detection in mammography and digital breast tomosynthesis using annotation-efficient deep learning approach


[Link](https://arxiv.org/abs/1912.11027v2)

## Key Takeaways

1. State of the art in mammogram classification
2. Can extend to 3D-mammogram
3. Generalizes well to other datasets
4. Outperforms trained imaging specialists
5. Could be potentially used in pre-diagnosis


## Key Points

### Datasets

* Uses both strongly labelled (bounding boxes) and weakly labelled data (breast level images)
* Severe class imbalances
* High resolution unlike ImageNet images

### Model

* Three stage model
* Stage-I trained on patches (contains a lesion or not, uses a pretrained ResNet-50)
* Stage-II uses RetinaNet which outputs a bounding box.
* State-III is targeted towards using weakly labelled data. (both 2D & 3D)
	* 	Uses a multiple instance learning formulation
	*  Trained with binary labels 

### Reader performance

* The great thing in this paper is that the model beats almost all the trained imaging specialists in identifying cancer.
* Not only that, the researchers used pre-cancerous false negatives and demonstrated that the model is still able to detect tumor. This represents a lost opportunity, these patients could have been given the treatment way before their actual detection of cancer.

