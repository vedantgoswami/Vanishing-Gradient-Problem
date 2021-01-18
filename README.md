# Vanishing-Gradient-Problem
Certain activation functions are added to neural networks, the gradients of the loss function approaches zero, making the network hard to train.

## Why This is a problem?
Certain activation functions, like the sigmoid function, squishes a large input space into a small input space between 0 and 1. Therefore, a large change in the input of the sigmoid function will cause a small change in the output. Hence, the derivative becomes small.

<img src="https://github.com/vedantgoswami/Vanishing-Gradient-Problem/blob/main/Images/Sigmoid.png">

### Lets have a look on this problem through the code:
I have used the sklearn dataset to train the neural network, Here is the dataset:
<p align="center">
<img src="https://github.com/vedantgoswami/Vanishing-Gradient-Problem/blob/main/Images/dataset.png">
</p>

### Neural Network model Summery
<p align="center">
<img src="https://github.com/vedantgoswami/Vanishing-Gradient-Problem/blob/main/Images/Model.PNG" width="50%">
</p>

Lets Concentrate on the first layer of the model
### <u>For Sigmoid</u>
<b>Weights before Training: </b><br>
[-0.1077401 ,  0.43455356, -0.60425615, -0.53927976, -0.190355,-0.12216991,  0.17259805, -0.29025432, -0.34041786,  0.5119183 ]

<b>Weights after 1st Epoch: </b><br>
[ 0.53107524,  0.12173636,  0.5073124 ,  0.54416114, -0.19135918,-0.08547983, 0.56848377,  0.44454524, -0.6231898 ,  0.0601779 ]

<b>Change in Weight</b><br>
[-0.00113249, -0.00108778, -0.00292063, -0.00071526, -0.00165403,-0.00002235, -0.00202656, -0.00181794,  0.00232458, -0.00081211]

As you can see that change in weight is very low, means that the weights and biases of the initial layers will not be updated effectively with each training session.
This can lead to overall inaccuracy of model.<br><br>

### One solution is Restricted Input:
Batch normalization reduces this problem by simply normalizing the input so |x| doesn’t reach the outer edges of the sigmoid function, it normalizes the input so that most of it falls in the green region, where the derivative isn’t too small.

<p align="center">
<img src="https://github.com/vedantgoswami/Vanishing-Gradient-Problem/blob/main/Images/restricted_input.png">
</p>

### Simplest solution is ReLU Activation:
It doesn't causes small derivative.
<p align="center">
 <img src="https://github.com/vedantgoswami/Vanishing-Gradient-Problem/blob/main/Images/derivative.png" width="48%">
  </p>
  
  
