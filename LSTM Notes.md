# What is LSTM?
**LSTM** is an enhanced version of RNN. Its main feature is capturing long-term dependencies in sequential data. This is accomplished via a memory cell that holds information over extended periods.

Like RNNs,  they have a chain of repeating modules that make up the network. Unlike RNNs, they have 4 different neural network layers, rather than just one. These 4 layers interact with each other in special ways.
## Why not an RNN?
RNNs struggle with handling data that has long-term dependencies where you need information from a previous, distant step. This results in either a **vanishing gradient** problem or an **exploding gradient** problem.
* The vanishing gradient problem is when the gradients shrink over the course of many steps. This makes past information more irrelevant, and therefore makes it difficult to learn long-term patterns
* The exploding gradient problem is when the gradient grows so large, every update becomes erratic and unstable.
## Architecture
### Cell State
The cell state runs continuously straight down the chain. It only has some minor interactions. Information can run down it with little to no changes.

Despite this, the LSTM can add or remove information to the cell state. 
### Memory Cell
The memory cell in an LSTM has three gates:
* An **input gate**, which controls what information is added to the memory cell.
* A **forget gate**, which controls what information is removed from the memory cell.
* An **output gate**, which controls what information is put out by the memory cell.
Using these, an LSTM can selectively retain or discard information.

