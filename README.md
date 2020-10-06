# Models for MNIST Classification

In this assignment, we will build three models for the digit recognition problem.  The data set will be the MNIST dataset,
and we will build three separate neural networks to recognize the single digits by performing 10-way classification.

We will analyze the three models, and use them to gain insights into the relative similarities of digits.

## The first model

The first model is a four-layer MLP, each layer has 10 neurons.  The final layer uses
`softmax` activation function, while all other layers use linear activation function.

The model summary is given as:
```
Model: "sequential"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
reshape (Reshape)            (None, 784)               0         
_________________________________________________________________
dense (Dense)                (None, 10)                7850      
_________________________________________________________________
dense_1 (Dense)              (None, 10)                110       
_________________________________________________________________
dense_2 (Dense)              (None, 10)                110       
_________________________________________________________________
dense_3 (Dense)              (None, 10)                110       
=================================================================
Total params: 8,180
Trainable params: 8,180
Non-trainable params: 0
_________________________________________________________________
```

## The second model

The second model has the same architecture as the first model, with the exception that
the inner layers use the non-linear `relu` activiation function.

The model summary is given as:

```
Model: "sequential_1"
_________________________________________________________________
Layer (type)                 Output Shape              Param #   
=================================================================
reshape_1 (Reshape)          (None, 784)               0         
_________________________________________________________________
dense_4 (Dense)              (None, 10)                7850      
_________________________________________________________________
dense_5 (Dense)              (None, 10)                110       
_________________________________________________________________
dense_6 (Dense)              (None, 10)                110       
_________________________________________________________________
dense_7 (Dense)              (None, 10)                110       
=================================================================
Total params: 8,180
Trainable params: 8,180
Non-trainable params: 0
_________________________________________________________________
```

Note that the second model's summary is the same as the first.  This is because Keras model summary does not
print out the activation functions used by the layers.

## The third model

The third model is a convolutional neural network with an architecture of convolution using 32 filters each 
with kernel size of (3, 3), **without** padding.  It is followed by a max-pooling layer with pooling size
of (2,2), and stride of (2,2), so that the neighbourhoods are not overlapping.  The output of max pooling
is processed by a dense layer of 10 neurons with softmax activation.

**NOTE**

> You are **not** allowed to use the `Flatten` layer.  In order to change the same of the tensors,
you must use the `Reshape` layer and provide explicitly the output shape.  This forces
you to think of the shape of the intermediate tensors.

# Training

For each model, train each model with cross-validation using 10% of the training data.
The training must be done with 10 epochs, using the Adam optimizer.

You are to record the accuracy and cross validation accuracy for each epoch.

# Analysis

1. You are to plot the training and cross-validations over the epoches, and comment if
the model may have overfitted the training data by the end of training.

2. Report the test accuracy for all the models.

3. You will compute the confusion matrix https://en.wikipedia.org/wiki/Confusion_matrix for each model.

4. Based on the confusion matrices, report the most misclassified digit for each model.

5. Plot 9 samples of (in a 3X3 grid) of the **misclassified** instances of the digit 3.


=======
# Mnist_Training
AI training using Mnist data set
>>>>>>> d35cbf7bb4a1e9d066a562f04fcedeeb9015fddc
