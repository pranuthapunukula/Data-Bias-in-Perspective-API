# Data-Bias-in-Perspective-API

## Perspective API Exploration

1 Problem Introduction
_______________________

The biases I believe may exist in the model based on my intuitions are the decreased accuracy for the scoring of comments that use non-explicit toxic language and the mislabeling of negative comments as threats or hate when they’re actually made in a self-directed or non-pejorative way. The biases I think may exist based on public documentation about how the model was created are an automatic higher scoring for terms used to describe marginalized groups based even when not used negatively and certain terms holding the same negative value weight as others when not considered equivalent from a human-evaluated perspective. 

2 Dataset
__________

The dataset consists of Wikipedia comments made available by Jigsaw, a subsidiary of Google that created the Perspective tool. The dataset includes a unique comment id, the text of the comment, and a series of binary labels applied by human raters: "toxic," "severe_toxic," "obscene," "threat," "insult," and "identity_hate." The "score" column has been appended, which represents the toxicity score assigned to the comment text by the live version of the Perspective API. The data is available under a CC0 license.

3 Models and Techniques
_______________________

For this assignment, I hypothesize that Perspective is more likely to fail if the comment contains terms referring to sexuality and gender identity such as “gay”, “lesbian”, and "non-binary". I will consider a comment to have failed when it includes one of these terms, receives a toxicity score over 0.5, but isn’t flagged in any category by the content moderators. I have chosen 0.5 as the threshold for the model because most of the severe toxicity comments fall into the 0.5-0.9 range.

4 Results and Discussion
_________________________

I believe my results reject my hypothesis because the mean score for my chosen key words are significantly lower than 0.5. I believe this is the case because upon further research, this is a bias issue that has been addressed by the developers of the API. The low sample size could have an impact on the accuracy of my results, but in conjunction with the site’s acknowledgment of the potential biases in the training data, I believe my hypothesis is false. 

