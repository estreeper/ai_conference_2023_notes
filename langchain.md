Harrison Chase, CEO and Co-founder at LangChain
September 26th, 2023

People were connecting lang models to other source of data/computation

"Context-aware reasoning applications"

Bring the right context and ask it to reason over that

"can argue about whether it's reasoning or not"

4 types of context awareness
 - instruction prompting (encoding how it should respond directily in the model)
 - few shot examples, also good to capture "tone"
    - can dynamically select the examples that are relevant
 - retrieval-augmented generation (RAG)
 - fine-tuning

Reasoning
 - what happens between the input and the eventual output

5 types of reasoning
 - LLM call: input into box, answer to user. Really fast compared to other architectures
 - Chaining: generate query, look up docs, generate answer. Sequences are well-defined
 - Routing: use LLM to control how input is handled, i.e. routing to different prompts/models
 - Automatons/State Machines (also called Agents): uses looping structures 
 - Autonomous agents:

Sweep.dev: uses a plan/execute/evaluate loop i.e. for code generation

Difficulties:
 - orchestration
 - data engineering: providing the right context to the LLM in the right places, transform it appropriately
 - prompt engineering: lots of time spent on instruction set, examples, etc.
 - debugging: be able to see how data flows through the system
 - evaluation: human labelling, or generate inputs and outputs, or can use production traffic (which is generally best), can also bootstrap by having LLM generate data. Hard to judge generated text, can use humans or LLMs. Explicit feedback (thumbs up/down), implicit feedback (if they asked similar followup question it may indicate a bad response)
 - collaboration aspect: lots of non-engineers participating

Langchain has added a prompt playground
