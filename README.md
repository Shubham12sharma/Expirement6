EXPERIMENT NO. 1
AIM:
Design Mc-Culloch Pitts model for AND, OR functions.
THEORY:
The McCulloch-Pitts neural model, which was the earliest ANN model, has only two types ofCONCLUSION:
Hence, we can conclude that we can learn and study about Mc-Culloch Pitts model for binary
logic functions.
inputs — Excitatory and Inhibitory. The excitatory inputs have weights of positive magnitude
and the inhibitory weights have weights of negative magnitude. The inputs of the McCulloch-
Pitts neuron could be either 0 or 1. It has a threshold function as an activation function. So, the
output signal yout is 1 if the input ysum is greater than or equal to a given threshold value, else
0. The diagrammatic representation of the model is as follows:


CODE:
import numpy as np
np.random.seed(seed=0)
# generate random vector I, sampling from {0,1}
I = np.random.choice([0, 1], 3)
# generate random vector W, sampling from {-1,1}
W = np.random.choice([-1, 1], 3)
print(f'Input vector: {I}, Weight vector: {W}')
# matrix of inputs
input_table = np.array([
[0, 0], # both no
[0, 1], # one no, one yes
[1, 0], # one yes, one no
[1, 1] # both yes
])print(f'Input table:\n{input_table}')
dot = I @ W
print(f'Dot product: {dot}')
def linear_threshold_gate(dot: int, T: float) -> int:
"""Returns the binary threshold output"""
if dot >= T:
return 1
else:
return 0
T=1
activation = linear_threshold_gate(dot, T)
print(f'Activation: {activation}')


CONCLUSION:
Hence, we can conclude that we can learn and study about Mc-Culloch Pitts model for binary
logic functions.
