Azada Nova, Research Scientist, Google Deepmind
September 27th, 2023

Downsizing models
operator factorization
value quantization

Sparsification/pruning

Sparsification: two approaches model sparsity (per model) and ephemeral sparsity (per example)

Model sparsity:
 - weights, can be unstructured or structured (remove nuerons from network or block sparcity in matrices) which hardware can leverage
 - goal is to remove neuron from the network

They are very complex, requires a lot of labeled data, and lots of engineering effort to implement

Breakdown analysis of BERT

which are the most costly blocks? Feed forward part
Structured pruning by masking
3072 filters in BERT

Find the mask such that some the loss is minimal

Ephemeral

Is it posible to prune networks without retraining/fine tuning?

Without access to labeled data, how can you prune the model?

Is it: gradient free, retrain/finetune-free, supervision-free, pruning time <= 7min?

Weight-Magnitude
Kernelized Convex Masking (theirs)

3 parts:
 - R2D2: applied on all 12 FF sections of BERT
   a. representative ranking (R2)
   b. data-driven (D2)
   get stats from weight, get stats from data, use for scoring function on FF layer
   eventually, scores are combined together
   finally, you have to scale up neurons to make up for the ones you lost

 Structured pruning goal: select a subset of data points as representative

 For linear functions, ,can be reduced to finding a convex hull (complexity O(N^d/2)
 Number of convex hull points radically increases with d

Therefore, use Kernelized Convex Hull Approximation

Data-Driven (D2)

term: majority voting

Convex hull only applies if you have a linear function, so to capture non-linearity make a full pass through the model to get the activations

Considers correlations between the layers (each layer has some information from previous layers)

i.e. only one layer vs. information from each layer

Ranking allows us to merge R2D2 together and determine what's important (rather than trial and error)
Dynamically detect which
 - merge and sort

Mask-tuning is supervised, KCM is unsupervised

What if you have some limited labeled data?

i.e. 512 and 1K labeled data

Did one forward-backward pass and gather the gradient over the mask variables, then refine top-k results

Can be done in less than 10 minutes

Achieved 40% FLOPs reduction with less than 4% accuracy loss over all tasks considered

Able to get 1.9x the speedup (so far) vs. existing methods
If you have larger LLMs, i.e. 30/60B, the effect is much higher and you get more speedup (it's harder to get it on smaller models)

Can a propogation error be introduced by pruning these filters?
 - yes, which is why we had to add this data-driven approach, because pruning applied only by later causes issues. If you only consider one layer and the convex hulll, error will propogate

What about things other than transformer models?
 - it would be applicable to any feed-forward method anywhere. You just need the W anywhere, it would be interesting to see for example in image models, but expect it would work there as well

Has this been implemented anywhere?
 - we want to make this open source, but it is not yet

How do you compare this versus model distillation?
 - distillation is practical and people use that a lot, but it needs a lot of labeled data and a lot of training to get there
 - with KCM you dynamically decide what to remove
