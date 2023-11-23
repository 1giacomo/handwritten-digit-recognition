# Handwritten digit recognition
Handwritten digit recognition (MNIST df) from sratch

## MNIST Database

## 2-Layer Neural Network

### Layer 0
784 nodes -> each one for a pixel

### Layer 1
10 nodes -> Hidden Layer

### Layer 2
10 nodes -> Output layer

## Training Network

### Forward propagation
$$
A^{[0]} = x
$$

$$
Z^{[1]} = W^{[1]}*A^{[1]} + b^{[1]}
$$

#### Apply an Activation Function

$$
A^{[1]} = g(Z^{[1]}) = ReLu(Z^{[1]})
$$

$$
A^{[1]} = g(Z^{[1]}) = \text{ReLu}(Z^{[1]})
$$

$$
\text{ReLu}(x) = \begin{cases} 
      x & \text{if } x \geq 0 \\
      0 & \text{if } x < 0 
   \end{cases}
$$

$$
Z^{[2]} = W^{[2]}*A^{[1]} + b^{[2]}
$$

#### Apply another Activation Function
$$
A^{[2]} = softmax(Z^{[2]})
$$


### Backward propagation
#### Layer 2
$$
dZ^{[2]} = A^{[2]} - Y
$$

$$
dW^{[2]} = 1/m*dZ^{[2]} * A^{[1]T}
$$

$$
db^{[2]} = 1/m*\sum_{}dZ^{[2]}
$$

#### Layer 1
$$
dZ^{[1]} = W^{[2]T} * dZ^{[2]} * g'(Z^{[1]})
$$

$$
dW^{[1]} = 1/m*dZ^{[1]} * X^T
$$

$$
db^{[2]} = 1/m*\sum_{}dZ^{[1]}
$$