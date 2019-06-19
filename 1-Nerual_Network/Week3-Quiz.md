## Question 1
Which of the following are true? (Check all that apply.)  
- [x] $a_4^{[2]}$ is the activation output by the $4^{th}$ neuron of the $2^{nd}$ layer
- [x] $a^{[2]}$ denotes the activation vector of the $2^{nd}$ layer
- [ ] $a^{[2](12)}$ denotes the activation vector of the $12^{nd}$ layer on the $2^{nd}$ training example
- [ ] X is matrix in which each row is one training example
- [x] $a^{[2](12)}$ denotes the activation vector of the $2^{nd}$ layer on the $12^{nd}$ training example
- [ ] $a_4^{[2]}$ is the activation output by the $2^{nd}$ neuron of the $4^{th}$ layer
- [x] X is matrix in which each column is one training example
## Question 2
The tanh activation usually works better than sigmoid activation function for hidden units   
because the mean of its output is closer to zero, and so it centers the data better for   
the next layer. True/False?
- [x] True
- [ ] False

## Question 3
Which of these is a correct vectorized implementation of forward propagation for layer $l$, where $1 \leq l \leq L$ ?
- [ ] $Z^{[l]}=W^{[l]}A^{[l]} + b^{[l-1]}$  
      $A^{[l]}=g^{[l]}(Z^{[l]}))$

- [ ] $Z^{[l]}=W^{[l]}A^{[l]} + b^{[l]}$  
      $A^{[l+1]}=g^{[l]}(Z^{[l]}))$

- [x] $Z^{[l]}=W^{[l]}A^{[l-1]} + b^{[l]}$  
      $A^{[l]}=g^{[l]}(Z^{[l]}))$

- [ ] $Z^{[l]}=W^{[l]}A^{[l]} + b^{[l]}$  
      $A^{[l+1]}=g^{[l+1]}(Z^{[l]}))$
      
## Question 4
You are building a binary classifier for recognizing cucumbers (y=1) vs. watermelons (y=0).   
Which one of these activation functions would you recommend using for the output layer?
- [ ] ReLU
- [ ] leaky ReLU
- [x] sigmoid
- [ ] tanh
## Question 5
Consider the following code:
```
A = np.random.randn(4,3)
B = np.sum(A, axis = 1, keepdims = True)
```
What will be B.shape? (If you’re not sure, feel free to run this in python to find out).  
- [ ] (,3)
- [ ] (4, )
- [x] (4, 1)
- [ ] (1, 3)
## Question 6
Suppose you have built a neural network. You decide to initialize the weights and biases to be zero.   
Which of the following statements is true?

- [x] Each neuron in the first hidden layer will perform the same computation. So even after multiple iterations of gradient descent each neuron in the layer will be computing the same thing as other neurons.
- [ ] Each neuron in the first hidden layer will perform the same computation in the first iteration. But after one iteration of gradient descent they will learn to compute different things because we have “broken symmetry”.
- [ ] Each neuron in the first hidden layer will compute the same thing, but neurons in different layers will compute different things, thus we have accomplished “symmetry breaking” as described in lecture.
- [ ] The first hidden layer’s neurons will perform different computations from each other even in the first iteration; their parameters will thus keep evolving in their own way.
## Question 7
Logistic regression’s weights w should be initialized randomly rather than to all zeros, because if you initialize to all zeros, then logistic regression will fail to learn a useful decision boundary because it will fail to “break symmetry”, True/False?
- [ ] True  
- [x] False  
**Hint**:  
Logistic Regression doesn't have a hidden layer. If you initialize the weights to zeros, the first example x fed in the logistic regression will output zero but the derivatives of the Logistic Regression depend on the input x (because there's no hidden layer) which is not zero. So at the second iteration, the weights values follow x's distribution and are different from each other if x is not a constant vector.

## Question 8
You have built a network using the tanh activation for all the hidden units. You initialize   
the weights to relative large values, using np.random.randn(..,..)*1000. What will happen?


- [ ] This will cause the inputs of the tanh to also be very large, thus causing gradients to also become large. You therefore have to set $\alpha$ to be very small to prevent divergence; this will slow down learning.
- [ ] This will cause the inputs of the tanh to also be very large, causing the units to be “highly activated” and thus speed up learning compared to if the weights had to start from small values.  
- [x] This will cause the inputs of the tanh to also be very large, thus causing gradients to be close to zero. The optimization algorithm will thus become slow.  
- [ ] It doesn’t matter. So long as you initialize the weights randomly gradient descent is not affected by whether the weights are large or small.  
**Hint**:   
It matters, remember that when the inputs of a tanh is far from zero, its gradient is very close to zero (because of flat edges of tanh).

## Question 9
Consider the following 1 hidden layer neural network:

$x_1$ ->   $\alpha_1^{[1]}$  
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;.  
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;. &ensp; &ensp; &ensp; &ensp; &ensp; -> $\alpha_2^{[1]}$  &ensp; &ensp; -> $\hat y$  
&ensp;&ensp;&ensp;&ensp;&ensp;&ensp;.     
$x_2$ ->  $\alpha_4^{[1]}$  

Which of the following statements are True? (Check all that apply).


- [ ] $W^{[1]}$ will have shape (2, 4)

- [x] $b^{[1]}$ will have shape (4, 1)

- [x] $W^{[1]}$ will have shape (4, 2)

- [ ] $b^{[1]}$ will have shape (2, 1)

- [x] $W^{[2]}$ will have shape (1, 4)

- [ ] $b^{[2]}$ will have shape (4, 1)

- [ ] $W^{[2]}$ will have shape (4, 1)

- [x] $b^{[2]}$ will have shape (1, 1)
## Question 10
In the same network as the previous question, what are the dimensions of $Z^{[1]}$
and $A^{[1]}$ ?

- [ ] $Z^{[1]}$ and $A^{[1]}$ are (4,1)  
- [ ] $Z^{[1]}$ and $A^{[1]}$ are (1,4)  
- [ ] $Z^{[1]}$ and $A^{[1]}$ are (4,2)  
- [x] $Z^{[1]}$ and $A^{[1]}$are (4,m)