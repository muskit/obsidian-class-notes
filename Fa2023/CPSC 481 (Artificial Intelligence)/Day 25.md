# Neural Networks
Human brains...
- are capable of **pattern recognition**.
- compute slowly and unreliably in parallel
Computers...
- have a single CPU (*multi-core*?) capable of extremely fast reliable computations

## Biological Neural Networks
**multi-layer** neural network
- allows for very complex functions
- consists of **biological neurons**

## Artificial Neurons
a **mathematical function** acting like a biological neuron
- input comes from other neurons, output depends on that input and some threshold
	- weight: input gets multiplied by this value before being considered
	- bias: value that is added to the weighted input to adjust
	- both $w$ and $b$ are adjusted based on true value and predicted value (error)

## Artificial Neural Networks (ANN)
*or just "neural networks"*

**Consists of layers**  
- input
- hidden
	- input passes through here before being outputted
	- bias and weight
- output

***Deep Neural Network (DNN)***- an ANN with **2+ hidden layers**
- 1 hidden layer is considered a *shallow neural network*

Typically used on supervised learning, but has been moving towards un- and semi-supervised recently.

## Convolutional Neural Network (CNN)
make predictions on *spatial* info
- topological, geometric, geographic

allows for focusing on smaller parts of data to make more accurate predictions
- remove meaningless data
- ex: when identifying a bird, we can ignore the background, the object it's standing on, other environment objects, etc

Layers
- Convolutional- filters to highlight important features (creates "feature maps")
	- 
- Pooling- reduce spatial dimensions of feature map
- Flattening- reduce dimensionality (ie. 2D to 1D)
- Fully Connected- classify this flattened vector