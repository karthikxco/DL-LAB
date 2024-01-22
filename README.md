Lab 1: Write a program to implement McCulloch-Pitts algorithms for realizing the    
             AND/OR logic functions. 
 
class McCullochPittsNeuron: 
    def __init__(self, weights, threshold): 
        self.weights = weights 
        self.threshold = threshold 
    def activate(self, inputs): 
        weighted_sum = sum([inputs[i] * self.weights[i]  
        for i in range(len(inputs))]) 
        return 1 if weighted_sum >= self.threshold else 0 
 
# AND Logic Function 
and_weights = [1, 1] 
and_threshold = 2 
and_neuron = McCullochPittsNeuron(and_weights, and_threshold) 
 
# OR Logic Function 
or_weights = [1, 1] 
or_threshold = 1 
or_neuron = McCullochPittsNeuron(or_weights, or_threshold) 
 
# Test AND logic function 
input_values_and = [(0, 0), (0, 1), (1, 0), (1, 1)] 
print("AND Logic Function:") 
for inputs in input_values_and: 
    output = and_neuron.activate(inputs) 
    print(f"Input: {inputs}, Output: {output}") 
# Test OR logic function 
input_values_or = [(0, 0), (0, 1), (1, 0), (1, 1)] 
print("\nOR Logic Function:") 
for inputs in input_values_or: 
    output = or_neuron.activate(inputs) 
    print(f"Input: {inputs}, Output: {output}") 
