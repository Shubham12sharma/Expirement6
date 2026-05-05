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
# Mc-Culloch Pitts Model for AND and OR Gates

import numpy as np

# Threshold activation function
def linear_threshold_gate(dot, T):
    if dot >= T:
        return 1
    else:
        return 0

# Input combinations
input_table = np.array([
    [0, 0],
    [0, 1],
    [1, 0],
    [1, 1]
])

print("Input Table:\n", input_table)

# -------- AND Gate --------
print("\nAND Gate:")
weights_and = np.array([1, 1])
threshold_and = 2

for row in input_table:
    dot = np.dot(row, weights_and)
    output = linear_threshold_gate(dot, threshold_and)
    print(f"Input: {row}, Dot Product: {dot}, Activation: {output}")

# -------- OR Gate --------
print("\nOR Gate:")
weights_or = np.array([1, 1])
threshold_or = 1

for row in input_table:
    dot = np.dot(row, weights_or)
    output = linear_threshold_gate(dot, threshold_or)
    print(f"Input: {row}, Dot Product: {dot}, Activation: {output}")


CONCLUSION:
Hence, we can conclude that we can learn and study about Mc-Culloch Pitts model for binary
logic functions.
