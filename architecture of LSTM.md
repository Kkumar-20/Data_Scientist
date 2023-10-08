The architecture of LSTM:
LSTMs deal with both Long Term Memory (LTM) and Short Term Memory (STM) and for making the calculations simple and effective it uses the concept of gates.

Forget Gate: LTM goes to forget gate and it forgets information that is not useful.
Learn Gate: Event ( current input ) and STM are combined together so that necessary information that we have recently learned from STM can be applied to the current input.
Remember Gate: LTM information that we haven’t forget and STM and Event are combined together in Remember gate which works as updated LTM.
Use Gate: This gate also uses LTM, STM, and Event to predict the output of the current event which works as an updated STM.


1. Forgetting Mechanism: Forget all scene related information that is not worth remembering.


Ready to start your data science journey?
Master 23+ tools & learn with guided projects with the Certified AI & ML BlackBelt Plus Program

2. Saving Mechanism: Save information that is important and can help in the future.

Now that we know when to use LSTMs, let’s discuss the basics of it.

 

The architecture of LSTM:
LSTMs deal with both Long Term Memory (LTM) and Short Term Memory (STM) and for making the calculations simple and effective it uses the concept of gates.

Forget Gate: LTM goes to forget gate and it forgets information that is not useful.
Learn Gate: Event ( current input ) and STM are combined together so that necessary information that we have recently learned from STM can be applied to the current input.
Remember Gate: LTM information that we haven’t forget and STM and Event are combined together in Remember gate which works as updated LTM.
Use Gate: This gate also uses LTM, STM, and Event to predict the output of the current event which works as an updated STM.
Remember Gate LSTMFigure: Remember Gate
Source: Udacity
The above figure shows the simplified architecture of LSTMs. The actual mathematical architecture of LSTM is represented using the following figure:

LSTM Architecture
Figure: LSTM Architecture
don’t go haywire with this architecture we will break it down into simpler steps which will make this a piece of cake to grab.

 

Breaking Down the Architecture of LSTM:
1. Learn Gate:  Takes Event ( Et ) and Previous Short Term Memory ( STMt-1 ) as input and keeps only relevant information for prediction.

Learn Gate LSTM
Figure: Learn Gate
Calculation:
LSTM Learn gate calculation
Source: Udacity
Previous Short Term Memory STMt-1 and Current Event vector Et are joined together [STMt-1, Et] and multiplied with the weight matrix Wn having some bias which is then passed to tanh ( hyperbolic Tangent ) function to introduce non-linearity to it, and finally creates a matrix Nt.
For ignoring insignificant information we calculate one Ignore Factor it, for which we join Short Term Memory STMt-1 and Current Event vector Et and multiply with weight matrix Wi and passed through Sigmoid activation function with some bias.
Learn Matrix Nt and Ignore Factor it is multiplied together to produce learn gate result.
 

2. The Forget Gate: Takes Previous Long Term Memory ( LTMt-1 ) as input and decides on which information should be kept and which to forget.

Forget Gate LSTm
Figure: Forget Gate
Calculation:

Source: Udacity
Previous Short Term Memory STMt-1 and Current Event vector Et are joined together [STMt-1, Et] and multiplied with the weight matrix Wf and passed through the Sigmoid activation function with some bias to form Forget Factor ft.
Forget Factor ft is then multiplied with the Previous Long Term Memory (LTMt-1) to produce forget gate output.
 

3. The Remember Gate: Combine Previous Short Term Memory (STMt-1) and Current Event (Et) to produce output.

The Remember Gate
Figure: Remember Gate
Calculation:
The Remember Gate calculation
Source: Udacity
The output of Forget Gate and Learn Gate are added together to produce an output of Remember Gate which would be LTM for the next cell.
 

4. The Use Gate:
Combine important information from Previous Long Term Memory and Previous Short Term Memory to create STM for next and cell and produce output for the current event.

use gate lstm
Calculation
use gate calculation

Previous Long Term Memory ( LTM-1) is passed through Tangent activation function with some bias to produce Ut.
Previous Short Term Memory ( STMt-1 ) and Current Event ( Et)are joined together and passed through Sigmoid activation function with some bias to produce Vt.
Output Ut and Vt are then multiplied together to produce the output of the use gate which also works as STM for the next cell.
Now scroll up to the architecture and put all these calculations so that you will have your LSTM ready.
