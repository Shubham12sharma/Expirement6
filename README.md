Title

Implementation of Mc-Culloch Pitts Neuron Model for Binary Logic Functions

Aim

To implement the Mc-Culloch Pitts neuron model to simulate basic binary logic functions like AND, OR, and NOT.

Theory (Short)

The Mc-Culloch Pitts (MCP) neuron is the simplest mathematical model of a biological neuron. It works on binary inputs (0 or 1) and produces a binary output.

Each input has a weight
A threshold (θ) is defined

The neuron computes:

y={1,
   0,    if ∑(wixi)≥θ
            otherwise
	​

It is used to implement logic gates:
AND gate
OR gate
NOT gate



code :


# Mc-Culloch Pitts Neuron Model

def mcp_neuron(inputs, weights, threshold):
    summation = sum(i * w for i, w in zip(inputs, weights))
    if summation >= threshold:
        return 1
    else:
        return 0

# AND Gate
print("AND Gate")
for x1 in [0, 1]:
    for x2 in [0, 1]:
        output = mcp_neuron([x1, x2], [1, 1], 2)
        print(x1, x2, "->", output)

# OR Gate
print("\nOR Gate")
for x1 in [0, 1]:
    for x2 in [0, 1]:
        output = mcp_neuron([x1, x2], [1, 1], 1)
        print(x1, x2, "->", output)

# NOT Gate
print("\nNOT Gate")
for x in [0, 1]:
    output = mcp_neuron([x], [-1], 0)
    print(x, "->", output)

Conclusion

The Mc-Culloch Pitts model successfully implements basic logic gates using weighted inputs and threshold values. It demonstrates how simple neurons can perform logical operations, forming the foundation of neural networks.
