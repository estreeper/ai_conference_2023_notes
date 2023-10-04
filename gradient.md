Mark Huang, co-founder chief architect Gradient
September 27th, 2023

LLM developer platform

There are 11.9B cellular connections, vs 8.1B population

Prediction: there will be more AI models than humans in 10 years

100B parameters leads to "breakthroughs" on common tasks

But... some tasks break down with more parameters (there is no free lunch)

$.50/hour per H100 GPU
70B parameter model
100 million tokens (about 24k full samples) = $3,500/experiment

Rapidly rising costs + diminishing returns

Textbooks is All You Need (Google Paper)
1.3B phi fine-tuned outperformed GPT 3.5 on code generation human eval

GPT 3.5 is very flexible, but targeted fine-tuning can outperform

large models have sparse pathways, very few are activated

Architecture should be mixture-of-experts

MoE: Cluster-Branch-Train-Merge

LSTM used to be state of the art

cluster data, take main language model, further train it on each cluster, then route it based on that

Can embed entire set of data (get labels + vector embeddings)

Embed enterprise corpus, embed it (i.e. BGE), find your experts

Experts as Adapters
 - sparse networks discovered without labels
 - performance increases with more data and more experts
 - Low Ran Adaptation (LoRA) is critical
   - lower training costs (4x less)
   - faster expert switching at runtime

Cold boot problem: when you need to reload a new model

Seed LLM (base model), i.e. Llama 2
LoRA Adapter (Finance, Engineering, Product, Operations)
Router (embeddings)

Prompt -> Embedding probabilities -> Top-K -> Merge

What is blocking this future?
 - complex infrastructure (distributed systems)
 - complex development (each model requires pre-training, etc.)
 - high cost (GPU costs, multi-tenancy)

Gradient wants to create an AI cloud
 -> one cloud to host many models
 -> simplify model development

