# SNN-perceptrons-implement-logical-gates-
A simple perceptron has been designed using Brian2, with a neuron model based on a leaky integrate-and-fire model. Two input neurons and one output neuron have been utilized to demonstrate that the perceptron is capable of performing AND, OR, NAND, and NOR operations.
# Install Brian2 in Colab
![1](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/1.png)
# LIF model
The following equation is the mathematical formulae of the LIF model:  
![LIF model](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/LIF%20model.png)  
When there is external input 𝐼 the equilirrium potential of the memrrane potential will increase. Once the memrrane potential exceeds a given threshold a spike occurs and the memrrane potential is reset to a specific reset potential.
#Modeling construction
![neuron](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/neuron.png)  
Because we need to construct a network with two inputs and one output I set n = 3 in the NeuronGroup() function and used the equation I defined in the previous 
section.  
The equation has three variarles: 𝑣0,𝑡𝑎𝑢𝑚,𝐼.  
I set 𝑣0 = [2,2,0] and 𝑡𝑎𝑢𝑚 = [20,20,200] ∗ 𝑚𝑠. Neuron0 and Neuron1 would re define as input1 and input2 respectively.  
The values I set for 𝑣0 and 𝑡𝑎𝑢𝑚 for Neuron0 and Neuron1 mean that they can fire pulses at a higher rate. Neuron2 is defined as the output and the values I set for 𝑣0 and 𝑡𝑎𝑢𝑚 in Neuron2 mean that if there are no synapses connected to it it will never fire a pulse.  
The variarle 𝐼 is the variarle I changed in the implementation of the different logic gates.  
The pre- and post-neurons in the synapse model are the same.  
The weight I set is rased on logic gates where different gates have different weights.  
The connection retween two synapses is such that roth input1 and input2 are connected to the output.  
# Parameters tuning
