# Network Details #
## Neurons ##
The neurons we should be using should be simple neurons that take a weighted input from the output of the previous layer. 2 functions to consider would be the sigmoid function and tanh. Output is just output of the function.

## Pre and Post Processing ##
There are two pre and postprocessing methods that I know of. For both we need to know an acceptable range of values that each input node in layer 0 will recieve. We need this because tanh and the sigmoid function are only interesting in a certain range. The two methods are:
  1. **Mean and Standard Deviation**
> > The means and standard deviation of a large sample set of input data is used to shift the input data over such that the mean and standard deviation lie within an interesting range.

> 2. **Max and Min**
> > Large set of sample input data for each neuron is evoluated, then scale and shift it such that the max and min lie within a specific range. This method sucks if you have statistical outliers.

The postprocessing methods are pretty much the same. Say one output neuron specified how much to turn the turret, we want to transform it such that it has a max of 360 and min of 0, or something along those lines (or +180 and -180 if we want to be efficient with out time...)

## Bias Nodes ##
We should add a single bias node at each layer that just fires 1, this helps stabilize any bumps we have in our network. It makes learning more efficient also. Bias nodes receive. When programming we'll just have it inherit from a basic node, and override the getOutput function.