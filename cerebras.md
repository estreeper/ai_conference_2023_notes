Andy Hock, PhD, VP Product, Cerebras Systems
September 27th, 2023

"Training larger, more accurate models with less compute"

LLM/GenAI have transformative potential for enterprise

How do you figire out how to build the right model? What do I use, how much data do I need, how do I tokenize, train from scratch vs. fine tune, infrastructure, etc.

Often takes hundreds of people weeks/months/years to build SOTA models

Building a compute platform, purpose-built chip, ML solutions engineering/pro services

850k programmable cores, 40GB on-chip memory

"Cluster-scale AI in a single chip"

Can run even the largest models on a single node

Cerebras-GPT
 - family of state of the art GPTs
 - trained on the Pile

Can predict test loss versus compute budget

High quality data matters

SlimPajama (Red Pajama cleaned/de-duplicated)

627B tokens
highest quality open-source English dataset available

BTLM-3B-8K can fit on a RPi, beats every existing 3B model (outperforms some 7B)

Jais: Arabic, English, and Code, and is now the best performing Arabic open model

Went from kickoff to leading OS model in just a few weeks (trained on their Galaxy cluster)

Lessons learned:
 - scaling laws matter: right dataset but also sub-scale models to identiy right hyperparameters and architecture
 - predict downstream accuracy
 - work with the right partner
