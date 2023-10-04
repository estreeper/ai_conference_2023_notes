Ofer (last name?) Developer Relations at Vectara
September 27th, 2023

Mental model: there is a knowledge graph embedded in its weights
it's not really understandable with the "knowledge graph" is

Why do LLMs hallucinate?
 - you ask a question not in the knowledge graph
 - they're not trained to say "I don't know" or caveat their answer
 - they generate highly probable responses, not necessarily correct ones

Answer 2: it is in the knowledge graph but might include fictional content, or have subjective opinions/beliefs

Adressing hallucinations
 - improve training data (cleaner/less bias)
 - incorporate human feedback using RLHF or similar
 - improved prompting (chain of thought, tree of thought, react)
 - RAG

RAG
 - LLMs with your data
 - Use cases: question answering, chatbot/co-pilot
 - might use response validation (Nvidia Nemo Guardrails)
 - response might trigger an action (enterprise app automation) i.e Zapier, JIRA, Nition, Coda, Asana, Monday, email, etc.

Vectara has an Indexing API, and a Query API, which makes it easier to build generative AI applications

Why RAG?
 - private
 - less expensive to implement, like re-training or collecting human feedback
 - complementary to model improvements like RLHF or better LLMs

Doing RAG right: retrieval matters
 - critical to have the best retrieval engine possible
   - low recall: if the right facts are missing LLM has nothing to work with
   - low precision: if wrong facts are included, we add noise

 How?
  - optimatel chunking of source documents
  - SOTA embeddings model (English + other languages)

 Chunking strategies:
  - fixed chunking: pick a character size and use it, but breaks sentences in the middle
  - LlamaIndex/Langchain use recursive chunking
  - Vectara uses NLP chunking: finding the smallest chunks that will work well without adding too much noise
  - create small chunks that have clean semantic meaning, then augment text with additional text around it when providing to LLM

Embedding models
 - Vectara uses their own model Boomerang

Vectara says they can adjust the weights of different documents

Question from audience: how do you persist fine-grained access controls from tools like JIRA, etc.
 - it's possible but takes a lot of work, have to make sure something
