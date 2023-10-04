M Waleed Kadous, Chief Scientist at Anyscale
September 26th, 2023

LLMs: easy to demo, hard to productionize

Anyscale
  Company behind open source project Ray
  Provide LLMs as a service (Llama models)
  Ues LLMs to make products better
  Help customers deploy on Ray
  Price: $1/million tokens (Llama-2 70B)

What makes it hard to go from demo to production?
 - not hallucinating (TL;DR use RAG)
 - know your relevance (TL;DR use GPT4 evaluation)

Cost: GPT-4 is 30x the cost of Llama 2

But: Llama is not as good?

Depends on the task
 - about as good for summarization


A small fine-tuned model can sometimes outperform large general models
 - consider using smaller open-source models

i.e. Llama 2 7B can be fine-tuned to outperform GPT4 in creating SQL queries at 1/300th the cost

They still use GPT4 a lot for evaluation and for hard queries

Missing features:
 - smaller context windows (Anthropic has 100k)
 - Llama 2 has 4k or 16k
 - Function templates (but may be coming to open source)

Data and Privacy
 - are you comfortable sending data to OpenAI?
 - are you worried about explaining to users you're sending their data to OpenAI?
 - are there restrictions like GDPR that apply?

Llama 2 70b takes 4x A100 80GB GPUs to deploy

Self-hosted Software
 ray-llm Open Source

Self-hosted Llama 2 Models

Llama 2 tB: One g5.2xlarge is ~$7,000/yr

Lambda Labs: $70k/yr, breakeven is 70B tokens/year

Assisted self-hosted

Concluding on the difficulties
 - cost is a major concern
 - open models can save money without losing quality but are less polished

What does the future hold?
 3 predictions:
   - one taks requires many LLM calls and many LLMS (fine-tuned vs general, small vs. large, open vs. proprietary)
  - RAG will be default use of LLMs in enterprises (this one he says is obvious)
  - we haven't fully solved the model improvement over time, someone has to crack this. Hasn't talked to a single person who has talked about how to retrain their LLMs. How do we improve them over time?

Anyscale Doctor: uses many models in sequence

User Input -> Summarize (Llama 70B) -> Categorize (Llama 70B) -> Python Error (Code Llama) -> Dependency error (Code Llama) OR Infra error (Code Llama)

Fine-tuning doesn't help with facts, RAG does. You need both.
 - still rough points with RAG: eexpensive because of long context (typical input 2k tokens), precision/recall of returned info

Ray Assistant: uses a supervised classifier to decide whether to use OSS LLM or ChatGPT (95% go to OSS)

Not enough thought into closing the loop
 - how to correct an LLM?
 - definitely not fine-tuning
 - RAG with some kind of virtual document, but that feels indirect
 - a corrections vector DB?
 - need to think more broadly about tools to improve models over time

Waleeds hard-won Heuristics
 - protype with GPT4 (if it doesn't work with this it just won't work)
 - one LLM call does one job. One call for summarization, one for classification. LLMs can't chew gum and walk at the same time
 - Llama 2 70B is useful as a day-to-day LLM if you remember rule 2 (for English)
 - fine-tuning is for form, not facts. RAG is for facts.
