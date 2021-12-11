# Neural Network Terminologies (Part 2)

More terms I came across that I'm pretty sure I'll forget

# NLP

| acronym        |actual term | explanation   |
|-------------|-------------|-------------|
| RNN cell | recurrent neural network cell | outputs and the previous hidden state are fed in as inputs again to produce the hidden state at the next time step. The benefit is that the network can take in inputs of arbituary lengths. This is especially useful for language models, where the text can be of varying lengths |  
| bi-RNN | bidirectional-RNN | used to describe an architecture with 2 seperate RNNs. One for storing hidden states in a forward manner, and the other in reverse. This is used to encode information about the whole sequence of text, so that the model have access to both information it has seen and text in the future. (Useful for situations like text translation) | 
| encoder-decoder | aka sequence2sequence | two RNNs in sequence. The first RNN stores the information of the input into a vector/embedding. The vector is then fed into another RNN as the input to output a sequence of tokens. This is used in situations like question & answer/ dialog where the input and output sequences are of different lengths. | 
| LSTM cell | long short term memory cell | RNN but with gates (input, output, forget) to regulate the flow of information. Input for these gates are the same as RNN cells (input at current time step + hidden state from previous time step) This helps to tackle the problem with RNNs forgetting early information with long sequences of information. Each gate takes a value between 0-1 and multipied with the corresponding element to determine the firing strength. |
| GRU | gated recurrent unit | a simplied LSTM cell. Only have 2 gates (update and reset). No more hidden state. Reset gate regulates how much to forget. Update gate regualates how much information flows into the memory. |


# Cool things I learnt
A common way of measuring the similarity of two vectors is the dot product. What confused me early on was the mathematical notation. Now, I know it's just ![equation](https://latex.codecogs.com/png.image?%5Cdpi%7B110%7D%20%5Ctextbf%7Bp%7D%20%5Ccdot%20%5Ctextbf%7Bq%7D%20=%20%5Cmathbf%7Bp%7D%5E%5Cintercal%20%5Cmathbf%7Bq%7D)
