# Class Notes - Spring 2022 - Practical Machine Learning
Contact: Mark Sherman <shermanm@emmanuel.edu>

<!--ts-->
   * [Class Notes - Spring 2022 - Practical Machine Learning](#class-notes---spring-2022---practical-machine-learning)
   * [Lecture 2 - January 24, 2022](#lecture-2---january-24-2022)
      * [Teachable Machine and Transfer Learning](#teachable-machine-and-transfer-learning)
      * [Vocabulary](#vocabulary)

<!-- Added by: shermanm, at: Mon Jan 24 18:04:23 EST 2022 -->

<!--te-->
# Lecture 2 - January 24, 2022
* Homework was to read <https://observablehq.com/@nsthorat/how-to-build-a-teachable-machine-with-tensorflow-js>

* ML models are *function approximators*
    * think about functions from algebra: they take an input and give a specific output
    * functions map an input domain to an output domain

## Teachable Machine and Transfer Learning
* Teachable Machine uses *transfer learning*
    * TM uses *MobileNet,* a pre-trained model that can identify objects in photos based on 1000 pre-set categories
    * TM uses the output of MobileNet as the input to another model, which we train on our training data. 
    * Training TM:
        * it runs each training image through MobileNet, get the resulting logits vector
        * looks for patterns in the logits vectors of all the training data that make up that *class*
    * Using the TM model (you are trying to classify a new image to one of your classes):
        * it runs the new image through MobileNet, gets the resulting logits vector
        * uses the patterns it figured out from training to guess which class the image likely belongs to

Discussion Question for Comprehension:

> MobileNet (and ImageNet that it was based on) has over 170 categories for various dogs, but only 10 categories for fish. 
> Does this mean that the Teachable Machine has less efficacy in learning the two fish as classes versus two dogs?
>
>Example: 
>
>Experiment A: you have images of two different dogs. In a fresh TM project, you train one dog as Class 1 and the other dog as Class 2. 
>
>Experiment B: you have images of two different fish. In a fresh TM project, you train one fish as Class 1 and the other fish as ass 2. 
>
>Will Experiment A perform at better at identifying its two classes? Why or why not?


## Vocabulary
* Transfer Learning
    * Using a pre-trained model as a starting point to make a more specific model
    
* logits / logits vector
    * a list of categories representing a single item (such as an image)
    * the contents or character of the item (image) are represented by values for each potential character
    * The output of MobileNet is a logits vector (length = 1000, because MobileNet and ImageNet have 1000 categories)
* softmax
    * ALL WE NEED TO KNOW FOR NOW: the algorithm that gives each category a percentage likelihood, from 0-1. 
    * Softmax is the last step MobileNet does when producing an output.

TODO: *k-nearest neighbors*

