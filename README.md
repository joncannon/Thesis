Modelling tempo representation in the basal ganglia, and its role in sensorimotor synchronization.

Authors: Jacob Duda, Dr. Jonathan Cannon

Affiliations: McMaster University

Date: Completed over 2023-24 academic year

Contact: jacobduda38@gmail.com, cannoj9@mcmaster.ca

Description: This is the senior thesis completed by Jacob Duda for his neuroscience undergraduate degree. The goal of the project is to model a potential mechanism through which the basal ganglia could encode tempo during sensorimotor synchronization tasks (ie. tapping along to a metronome) and how this mechanism could explain some features seen in the tapping literature. 

The model takes two different forms. A simple bump attractor network containing excitatory and inhibitory connections designed to capture the general behavior of the basal ganglia. And a more complex multilayer neural network, which each layer represents a seperate component of the basal ganglia, and the connections between them are designed to implement the action selection model originally proposed by Gurney et al. (see included write-up for details).

'line_attractor_switching' contains the line attractor model simulating switching between two tempos of tapping (activated basal ganglia) loops. The code consists of a class called 'attractor', which is a single layer neural network with connectivity giving it the characteristics of a bump attractor. Each unit represents a CSNTC loop encoding tapping at a different tempo. The 'init' function takes various parameters which determine the activity and connectivity of the units. The 'run' function takes two inputs, a stimulus, and a dopamine sequence. The stimulus is an array of 0s and 1s, where array positions containing a 1 represent when an external tap occured (ie. when a metronome click was heard). All stimulus sequences for the code are defined in the first block. The dopamine sequence is an array containing values [0,1] which represent the relative amounts of dopamine released onto the striatum. The network takes input based on the previous inter-stimulus interval (ie. time between metronome clicks). The tempo with with the network than produces output 'taps' is determined by what the most active unit is in the network. The 'run' function will return various plots describing the activity of units, which tempos were selected at different time steps, and what the simulated inter-tap intervals were. 

'line_attractor_parkinsons' uses the exact same model as 'line_attractor_switching'. However, the 'run' function in the 'attractor' class has been simplified as not all the outputs are needed. Also, instead of receiving an array of stimulus timings, here the model is given a 'means' variable which is an array of where the mean of the input should be centered at each time step. Additionally, there is a new 'UO' function which simulates an Ornstein-Uhlenbeck process which we use to add random noise to the means. Then, the final code block simulates the activity of the network as it receives input with the noisy means. This is done at variable dopamine levels to investigate the stability of the network while receiving low dopamine, analagous to low dopamine seen in Parkinson's patients. 

'bg_model_switching' performs the same task as 'line_attractor_switching' but using a more complicated neural network model. Here, each subregion of the basal ganglia is represented as a single layer of units, and the connectivity between units is based on the segregation of CSNTC loops. The 'init' function takes the desired number of units ('n_units')in each layer as well as a variable defining the length of the simulation that will be performed ('n_time_steps'). The'run' function performs the exact same simulation and takes stimulus arrays in the same form as 'line_attractor_switching', however that there is no 'dopamine' input variable. Instead, the dopamine level is calculated each step based on error between the taps produced by the network and the observed stimulus. Within the network, the cortex (ctx) layer receives input in the same way as 'line_attractor_switching' and the tempo of tapping is determined bt the most active thalamic (tha) unit. Only the two striatal layers (sd1,sd2) have the activity of their units modulated by dopamine. The 'display' function then plots the activity of all the units throughout the simulation and displays the produced inter-tap intervals as well as which thalamic layer units were most active throughout the simulation. 

The 'rough_work' folder contains various previous versions of each model, as well as some work on other early models. They are being stored for potential later reference by the authors, but have not been designed to be readable and do not contain any information important to the models presented.

Dependencies: The code should not rely on any specific environment setups, as it only uses basic functions from numpy and scipy. However, it has been confirmed to work with...