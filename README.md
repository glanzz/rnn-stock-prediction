# Forecast Stock Price using Recurrent Neural Network + LSTM
# Parameter Choice
<table style="width:80%">
<tr>
<th>Paramter</th>
<th>Value</th>
<th>Understanding/Observation</th>
</tr>
<tr>
<td>Window size</td>
<td>58</td>
<td>Look back period, how many days to capture as a unit, Increasing the window size above 60 could not explain the last 30 days of increase in price.</td>
</tr>
<tr>
<td>Number of epochs</td>
<td>200</td>
<td>Increasing the epochs made the model more deterministic and reduced the loss in validation</td>
</tr>
<tr>
<td>Hidden Units</td>
<td>4</td>
<td>Decreasing the hidden units actually helped when we changed the activation function to tanh + ReLU. With hidden input layer</td>
</tr>
<tr>
<td>Activation Function</td>
<td>tanh + relu</td>
<td>Centering data and manages data in preferable range mapping from (-1 to 1) help capture dynamics, final layer is relu as it maps to (0, inf) which is nature of output price predicted.  </td>
</tr>
<tr>
<td>Batch size</td>
<td>10</td>
<td>Reduced it as the model was not able to generalize the last 30 days of the stock prices where it was struggling to predict. </td>
</tr>
</table>
<br/>
<br/>
<br/>


# Insights
The parameters direct the model to analyze the data by helping it understand the data in terms market and time period.<br/>
#### What does our data mean ?
Batch Size: 10 - Two weeks data per time step<br/>
Window: 58 - Look back 58 days of data to predict the next price<br/>
Epochs: 200 - Build memory to understand the data by looking 200 times<br/>
Hidden Units: 4 - Capture complex insights sooner<br/>
<br/>
Quarter is captured in window size, sprint is defined in batch size
<br/>
