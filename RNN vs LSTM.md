# Difference Between RNN and LSTM
 

- Recurrent Neural Networks RNNs

Recurrent layer feedback loops are a feature of RNNs. They are able to keep information in "memory" as a result.
Standard RNNs might be difficult to train to address issues that call for learning long-term temporal dependencies.
This is due to the loss function's gradient's exponential decrease over time (called the vanishing gradient problem).
Information isn't kept in the memory of an RNN for very long.


- Long Short-Term Memory LSTM
A form of RNN called LSTM networks employs special units in addition to conventional units.
A "memory cell" found in LSTM units is capable of storing data in memory for extended periods of time. They can learn longer-term dependencies thanks to this memory cell.
By adding new gates, such as input and forget gates, which improve control over the gradient flow and better preserve "long-range dependencies," LSTMs address the disappearing and expanding gradient difficulties.
Information is kept in the memory for a very long time by LSTM.

 

