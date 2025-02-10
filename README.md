# spam-filter-with-distilbert-and-gpt2

In this workbook we are going to train the two large language model Distilbert and GPT2 to classifying spam and non spam SMS. An obvious choice for this are BERt or Distilbert having a classification token which, after adding a classification head the to uncased mode, whether SMS are positive (spam) or negative (ham). GTP2 on the other hand, seems to be less suitable for such a case, as it is a decoder text generation transformer. Nevertheless, we are still trying to check whether we can build a GPT2 classifier.

In the first section we will train Distilbert as a classfier. Thereafter, we are slightly going to modify the training set in such a way that GPT2 can learn to decide whether an SMS is spam or not. The idea is the following: consider an example SMS

*'You just received 100 Bitcoins to your wallet'*     

with label *'Spam'*. We adjust the training data into

*'You just received 100 Bitcoins to your wallet --- This SMS is: Spam'*.
