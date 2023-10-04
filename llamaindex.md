Jerry Liu, Co-founder at LlamaIndex
September 26th, 2023

Basic RAG pipeline:
 Doc -> Chunks -> Vector Database (5 loc with LlamaIndex)

Find top-k most similar chunks

Challenges with "naive" RAG
 - failure modes
   - quality related (hallucination, accuracy)
   - non-quality related (latency, cost, syncing)
 - bad retrieval
  - low precision: not all chuns are relevant
    - hallucination + "lost in the middle" problems (LLMs tend to care less about stuff in the middle)
  - low recall: not all relevant chunks are retrieved
  - outdated information

Bad response generation
 - hallucination
 - irrelevange: makes an up answer that doesn't answer the question
 - bias/harmful outputs

What can we do?
 - data: store additional information beyond raw text chunks?
 - embeddings: optimize representation
 - retrieval: something better than top-k?
 - synthesis: use LLMs for more than generation?

But first we need to measure performance

Evaluation:
 - how to evaluate?
   - evaluate in isolation (retrieval, synthesis)
   - evaluate e2e
 Open question: what should we do first?

Collect dataset
 input: query
 output: ground-truth documents relevant to the query
Run retriever over dataset
Measure rankings in metrics

Synthetic dataset generation for retrieval evals

Parse/chunk up text corpus
Prompt GPT4 to generate questions from each chunk/subset of chunks
Each (question, chunk) is now your evaluation pair

Evaluation e2e

Collect dataset
 input: query
 (optional) output: the "ground-truth" answer
Run through full RAG pipeline
Collect evaluation metrics
 - if no labels, label-free evals
 = if labels, with-label evals

 Synthetic dataset generation for e2e evals: can also use GPT4

 LLM-based evaluation modules

 GPT4 is a good human grader
 Label-free modules
  - faithfulness: whether response matches retrived context
  - relevancy: whether response matches query
  - guidelines: whether response matches guidelines

 Techniques for better performing RAG
  - raw text chinks can bias your embedding representation with filler content

 Small-to-Big retrieval

 - embed text at a sentence-level, then expand window during LLM synthesis

 Embed references to text chunks
  - embed and retrieve based on smaller chunks, but pull in bigger chunks

 Heirarchical retrieval
  - Summaries -> documents
  - Embed larger documents via summaries

Look for "Production RAG Guide" on LlamaIndex

Fine-Tuning
 - can fine-tune embeddings of the LLM

Find-tuning (embeddings)
 - generate synthetic training query dataset from raw text chunks using LLMs
 - similar process to generating an evaluation dataset

Use this synthetic dataset to fine-tune an embedding model
 - directly funtune sentence_transformers model, or
 - finetune a black-box adapter (linear, NN, any neural network)

Can also freeze embeddings model, but fine-tune query embeddings
