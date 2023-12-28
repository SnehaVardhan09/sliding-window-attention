# sliding-window-attention
Visualize the sliding window attention receptive field


The receptive field comes from convolutional neural networks. It is the region in the input space that a particular CNN's feature is looking at. The receptive field is a function of the CNN's architecture and the number of layers and is a useful concept for understanding the CNN's feature extraction process.

This sliding window attention, we start with our input sequence, in which each token is represented by a vector. We then compute the attention using a sliding window of size w
. The output of the self-attention (computed by the final multiplication of the attention weights and the input sequence) is a weighted sum of the input sequence. In our case, I will represent the input as a sequence of set objects, such that each set represents the tokens from which information has been captured by the attention mechanism