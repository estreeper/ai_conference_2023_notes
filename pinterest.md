Note: I came into this 8 minutes late and didn't have much understanding of the
subject matter, these notes may be pretty bad

Aayush Mudgal, Senior Machine Learning Engineer at Pinterest
September 27th, 2023

Data quality based on downstream application
Want to optimize 

2014: used logistic regression model

2017: GBDT Model + LR (from a famous Facebook paper)

2018: Neural network model (deep and wide) - based on a paper from Google

2019: Pinterest's AutoML -> no more handcrafted features

Pinterest AutoML
1. 

Have to preprocess features for deep learning because otherwise it puts the model at risk

Representation layer

In 2020 iOS 14 was rolled out, which limited data advertisers could collect

There is a tradeoff between model size and label sparsity

Conversion optimization: landscape changes
 - ad created
 - early prediction (conversion 

Most users weren't willing to share their data, but can't match conversion events

2021: moved to a Deep Multitask NN Model

2022: PinnerFormer: learn users journey across the app over several months, feed into the model

2023: Crossing architecture

Personalization doesn't have to come at the expense of privacy

Landscape is moving to aggregate identities

Data deletion requirements
 - have to structure pipelines so you can control it in a scalable manner
 - model unlearning

Algorithmic advancements
 - handle sparse and noisy datasets
 - training on encrypted data and aggregated datasets
Data storage/privacy safe handling
 - access controls
Secure data sharing
 - share data between two parties without divulding private data
 - clean rooms: neutral party to measure efficacy

