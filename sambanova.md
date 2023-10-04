Urmish Thakker, Senior Engineering Manager, NLP, SambaNova Systems
September 27th, 2023

Create chips (5T parameters, 256k sequence length), full-stack solution

Took enterprises quite a long time to get in gear, but that change is happening now

Composition of Experts (CoE) model architecture
Larger memory unlocks multimodal capabilities

Closed source
 - very capabile, but difficult to inspect/verify, limited control of privacy, limited ability to tailor them

Open source
 - can lag behind closed source

Multilingual chat bot
Enhanced Bloom 176B

Instruction tuning over OIG

Got close to GPT4

Teaching LLMs to use software APIs
ChatGPT plugins: allowed LLM to access outside world
How can we bring this to open source LLMs?
 - how to benchmark them?

Going beyond individual models
 - need for specialization
   - solving specific/specialized tasks
   - domain expertise
   - context distillation: input length was too long, reduce prompt length
   - improve robustness: avoid prompt engineering used during proof of concepts
   - incorporate private data

 Number of experts required for an enterprise can grow quickly (just 15 70B experts = 1T parameters)

 Step 1: process input, break it down into sub-tasks based on expert availability (can use lookup table, or vectorization, or another model)
  - needs large/fast memory to store all the experts
 Step 2: load the right experts quickly
  - requires very high bandwidth to load the experts
Step 3: combine them to produce output
 - fast inference

SambaNova: 28x cheaper vs DGX100
