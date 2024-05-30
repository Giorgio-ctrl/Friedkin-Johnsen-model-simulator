# Friedkin-Johnsen-model-simulator


A module capable of simulating the spreading of an opinon in a given network using the Friedkin-Johnsen model.

## Table of contents

* [Requirements](#Requirements)
* [Installation](#Installation)
* [Usage](#Usage)


## Requirements

* Python 3.9.10 or higher
* Numpy 1.25.0 or higher

## Installation
Clone the repository:

```sh
git clone https://github.com/Giorgio-ctrl/Friedkin-Johnsen-model-simulator.git
```

## Usage

```sh
model = Friedkin_Johnsen(weight, influence)
```

* weight is the stochastic weighed adjacency matrix of the network (each element a<sub>ij</sub> is the influence of node j on node i)
* influence is the matrix where each diagonal element is how much a node is influenced by its original opinion and all the other entries are 0

```sh
model.simulate(initial)
```
* initial is the nx1 vector of the original opions of each node

This code altogether returns the opinions that the system converges to or -1 if they don't converge.
