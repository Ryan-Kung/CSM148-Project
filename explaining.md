## My Code 
Basically to briefly explain what my code consists of is

Firstly just EDA

Then its an attempt to use Lasso Regularization with logistic regression to do feature selection. My first attempt yielded all 0's for the coefficients so I tried doing this over more penalty terms and with less iterations to maybe lessen the penalization that was happening but it didn't work so I thought it just probably wasn't compatible with our data. 

After this I tried just logistic regression to classify just to show that its something we tried and as expected the accuracy is very low. 

Then I tried doing PCA because I thought this could be a good alternative to reducing redundancies in our data for when I did fit the neural network which was the goal. 

Finally I did the neural network, first with PCA but turns out doing it without PCA was just better. I try several combinations of layers and drop out rates. Probably talk about using early stopping, dropout, learning rate scheduler, and the architecture of the network. Also, since it was required to use cross-validation, I used k-fold to find an optimal drop-out rate for the final model which was the best. 

Also what the mapping is, is that I realized it was probably incredibly difficult for the model to distinguish between 114 genres when a lot of them are extremely similar (like rock vs. rock-n-roll, or electronic vs. edm, heavy-metal vs. metal, etc) which are distinct genres in our data set. So what I did was I made a new set of 12 genres that combined all the similar ones into one of these 12 overarching genres so that I could see if the model was at least getting similar genres so making close classifications. It got to 52% accuracy vs. 33% accuracy on the original when I mapped the last model's classifications to the smaller set of genres so not bad (random guessing amongst 12 genres for 2280 points (the 20% testing data) and getting 52% or more of them right is essentially 0).