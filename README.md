Modelling tempo representation in the basal ganglia, and its role in sensorimotor synchronization.

Authors: Jacob Duda, Dr. Jonathan Cannon

Affiliations: McMaster University

Date: Completed over 2023-24 academic year

Contact: jacobduda38@gmail.com, cannoj9@mcmaster.ca

Description: This is the senior thesis completed by Jacob Duda for his neuroscience undergraduate degree. The goal of the project is to model a potential mechanism through which the basal ganglia could encode tempo during sensorimotor synchronization tasks (ie. tapping along to a metronome) and how this mechanism could explain some features seen in the tapping literature. 

The model takes two different forms. A simple bump attractor network containing excitatory and inhibitory connections designed to capture the general behavior of the basal ganglia. And a more complex multilayer neural network, which each layer represents a seperate component of the basal ganglia, and the connections between them are designed to implement the action selection model originally proposed by Gurney et al. (see included write-up for details).

The repository also contains some previous work on building an echo-state neural network and replicating the basal ganglia model designed by Mannella and Baldassare (see write-up). This code is stored in this repository for potential later use, but does not have any role in the general conclusions of the project. 

The code should not rely on any specific environment setups, as it only uses basic functions from numpy and scipy. However, it has been confirmed to work with...