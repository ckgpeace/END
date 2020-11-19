#### Notebook: Session4_1:
This file contains accuracy **88.3%** percent on test data
Following changes has been made in the file:
1. number of layers has been changed from 1 to 3
2. Number of training epochs 5 to 10
3. Droup out value = 0.5

#### Notebook: Session4_2:
I tried stacking LSTM layers. I was not able to run the training due following:

'''
RNN
(
  (embedding): Embedding(25002, 100, padding_idx=1)
  
  (rnn1): LSTM(100, 256, num_layers=3, dropout=0.5, bidirectional=True)
  
  (rnn2): LSTM(256, 256, num_layers=3, dropout=0.5, bidirectional=True)
  
  (rnn3): LSTM(256, 256, num_layers=3, dropout=0.5, bidirectional=True)
  
  (fc): Linear(in_features=512, out_features=1, bias=True)
  
  (dropout): Dropout(p=0.5, inplace=False)
  
)

'''

***I got error - "RuntimeError: input.size(-1) must be equal to input_size. Expected 256, got 512" in the training block

This error was due to improper input to subsequent LSTM layer from first one.


