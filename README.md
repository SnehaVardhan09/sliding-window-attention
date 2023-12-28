# sliding-window-attention
Visualize the sliding window attention receptive field


The receptive field comes from convolutional neural networks. It is the region in the input space that a particular CNN's feature is looking at. The receptive field is a function of the CNN's architecture and the number of layers and is a useful concept for understanding the CNN's feature extraction process.

This sliding window attention, we start with our input sequence, in which each token is represented by a vector. We then compute the attention using a sliding window of size w
. The output of the self-attention (computed by the final multiplication of the attention weights and the input sequence) is a weighted sum of the input sequence. In our case, I will represent the input as a sequence of set objects, such that each set represents the tokens from which information has been captured by the attention mechanism


Initially, the sequence is a list of sets, all containing a single token.

Layer  input:
0: ['the']
1: ['cat']
2: ['is']
3: ['on']
4: ['a']
5: ['chair']
After the first layer, considering a sliding window size of 3, the output of the attention mechanism is:

Layer 1 output:
0: ['the']
1: ['the', 'cat']
2: ['the', 'cat', 'is']
3: ['cat', 'is', 'on']
4: ['is', 'on', 'a']
5: ['on', 'a', 'chair']
The output of the first layer becomes the input of the second layer. The output of the second layer is:

Layer 2 output:
0: ['the']
1: ['the', 'cat']
2: ['the', 'cat', 'is']
3: ['the', 'cat', 'is', 'on']
4: ['the', 'cat', 'is', 'on', 'a']
5: ['cat', 'is', 'on', 'a', 'chair']


As we can see, even with a sliding window of size 3, after just two layers, the attention mechanism can capture long-range dependencies. This is because the output of the first layer is used as the input of the second layer, and the attention mechanism is applied again. This is similar to the idea of stacking multiple layers of CNNs to increase the receptive field.