# SNN-perceptrons-implement-logical-gates-
A simple perceptron has been designed using Brian2, with a neuron model based on a leaky integrate-and-fire model.  
Two input neurons and one output neuron have been utilized to demonstrate that the perceptron is capable of performing AND, OR, NAND, and NOR operations.
# Install Brian2 in Colab
![1](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/1.png)
# LIF model
The following equation is the mathematical formulae of the LIF model:  
![LIF model](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/LIF%20model.png)  
When there is external input 𝐼 the equilirrium potential of the memrrane potential will increase. Once the memrrane potential exceeds a given threshold a spike occurs and the memrrane potential is reset to a specific reset potential.  
![initial set](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/LIF%20model%20set.png)
#Modeling construction
![neuron](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/neuron.png)  
Because we need to construct a network with two inputs and one output I set n = 3 in the NeuronGroup() function and used the equation I defined in the previous 
section.  

The equation has three variarles: 𝑣0,𝑡𝑎𝑢𝑚,𝐼
#### I set 𝑣0 = [2,2,0] and 𝑡𝑎𝑢𝑚 = [20,20,200] ∗ 𝑚𝑠  

### Neuron0 and Neuron1 would be define as input1 and input2 respectively.
### Neuron2 is defined as the output.  

1. The values I set for 𝑣0 and 𝑡𝑎𝑢𝑚 for Neuron0 and Neuron1 mean that they can fire pulses at a higher rate. 
The values I set for 𝑣0 and 𝑡𝑎𝑢𝑚 in Neuron2 mean that if there are no synapses connected to it it will never fire a pulse.  
2. The variarle 𝐼 is the variarle I changed in the implementation of the different logic gates.  
3. The weight I set is rased on logic gates where different gates have different weights.  
# Parameters tuning
The truth tarle of different logic gates are in the following figure:  
![truth table](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/truth%20table.png)  
## 1. AND GATE
When the inputs or the output need to fire I set 𝐼 = 2;  
when they don’t need to fire I set 𝐼 = 0.  

The weight is set to -0.000001 which means that when neuron2 (the output) is activated the rate of increase of the 𝑣_𝑡ℎ𝑟𝑒𝑠ℎ𝑜𝑙𝑑 is very slow so either input1 or input2 = 1 the output would be fired.  

When both input1 and input2 = 0 output would be fired in a slow rate.  
![and](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/AND%20GATE.png)  
## 2. OR GATE
When the inputs or the output need to fire I set 𝐼 = 2;  
when they don’t need to fire I set 𝐼 = 0.  

The weight is set to 0.1 which means that when neuron2 (the output) is activated the rate of increase of the 𝑣_𝑡ℎ𝑟𝑒𝑠ℎ𝑜𝑙𝑑 is very fast so either input1 or input2 = 1, the output would be fired.  
![or](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/OR%20GATE.png)  
## 3. NAND GATE
When the inputs or the output need to fire I set 𝐼 = 2;  
when they don’t need to fire I set 𝐼 = 0.  
The weight is set to -0.000001 which means that when neuron2 (the output) is activated the rate of increase of the 𝑣_𝑡ℎ𝑟𝑒𝑠ℎ𝑜𝑙𝑑 is very slow so either input1 or input2 = 1, the output would be fired. 

When both input1 and input2 = 0 output would be fired in a slow rate.
![nand](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/NAND%20GATE.png)  
## 4. NOR GATE
When the inputs or the output need to fire I set 𝐼 = 2;  
when they don’t need to fire I set 𝐼 = 0.  
The weight is set to -0.000001 which means that when neuron2 (the output) is activated the rate of increase of the 𝑣_𝑡ℎ𝑟𝑒𝑠ℎ𝑜𝑙𝑑 is very slow so either input1 or input2 = 1, the output won’t be fired.  

When both input1 and input2 = 0 output would be fired in a slow rate.
![nor](https://github.com/hsieh672/SNN-perceptrons-implement-logical-gates-/blob/main/NOR%20GATE.png)  
