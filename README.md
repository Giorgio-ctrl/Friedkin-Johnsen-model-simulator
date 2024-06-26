# Friedkin-Johnsen-model-simulator


A module capable of simulating the spreading of an opinon in a given network using the Friedkin-Johnsen model.

## Table of contents

* [Requirements](#Requirements)
* [Installation](#Installation)
* [Usage](#Usage)
* [Example](#Example)


## Requirements

* Python 3.9.10 or higher
* Numpy 1.25.0 or higher

## Installation
Clone the repository:

```sh
git clone https://github.com/Giorgio-ctrl/Friedkin-Johnsen-model-simulator.git
```

or install via pip:

```sh
python -m pip install FJsim
```

## Usage

```sh
model = Friedkin_Johnsen(weight, influence)
```

* weight is the stochastic weighed adjacency matrix of the network (each element a<sub>ij</sub> is the influence of node j on node i)
* influence is the matrix where each diagonal element is how much a node is influenced by others and all the other entries are 0

```sh
model.simulate(initial)
```
* initial is the nx1 vector of the original opions of each node

This code altogether returns the opinions that the system converges to or -1 if they don't converge.


## Example


```sh
weight = np.array([
              [0.220, 0.120, 0.360, 0.300],
              [0.147, 0.215, 0.344, 0.294],
              [0.000, 0.000, 1.000, 0.000],
              [0.090, 0.178, 0.446, 0.286]
              ])
influence = np.diag([0.780, 0.785, 0, 0.714])
initial = np.transpose([25, 25, 75, 85])

model = Friedkin_Johnsen(weight, influence)
print(model.simulate(initial)
```
This code will print:
```sh
[60.02084883 59.98396594 75.         74.98620494]
```
Which is exactly the vector of the opinions once they converge.
