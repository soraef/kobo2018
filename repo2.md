# コード
```python
import numpy as np

def init_network():
    network={}
    network['W1'] = np.array([[0.1, 0.3, 0.5], [0.2, 0.4, 0.6]])
    network['b1'] = np.array([[0.1, 0.2, 0.3]])
    network['W2'] = np.array([[0.1, 0.4], [0.2, 0.5], [0.3, 0.6]])
    network['b2'] = np.array([[0.1, 0.2]])
    network['W3'] = np.array([[0.1, 0.3], [0.2, 0.4]])
    network['b3'] = np.array([[0.1, 0.2]])
    return network

def layer(W, x, b, func):
    a = np.dot(x, W) + b
    return func(a)

def identify_function(x):
    return x

def sigmoid(x):
    return 1 / (1 + np.exp(-x))

def forward(network, x):
    W1, W2, W3 = network['W1'], network['W2'], network['W3']
    b1, b2, b3 = network['b1'], network['b2'], network['b3']
    x2 = layer(W1, x, b1, sigmoid)
    x3 = layer(W2, x2, b2, sigmoid)
    y = layer(W3, x3, b3, identify_function)
    return y

network = init_network()
x=np.array([1.0,0.5])
y=forward(network,x)
print(y) #[0.31682708 0.69627909]
```

# 実行結果
[[ 0.31682708  0.69627909]]