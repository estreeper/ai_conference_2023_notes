Jeff Boudier, Product Director, Hugging Face
September 27th, 2023

"11 things about HF you probably didn't know"

HF has no partnership with CloudFlare on serverless GPUs

Mission: democratize good ML (open source, community-driven, ethics-first)

HF is an open source company
 - transformers
 - diffusers (image/audio generator models like StableDiffusion)
 - text-generation-inference
 - peft

Host 1M repositories with 300k free and public models

1M model downloads/day
1,000 open LLMs

30k checkpoints available for Llama on the hub

Open LLM leaderboard, MTEB leaderboard

HuggingChat: converse with the best open models (also open source - chat-ui-project)

Can get files directly from HF

Under the hood, these are all Git repos - can see who made the commits and when

You can also collaborate via the Community tab: can set it as public or private

You can also train them on HF
 - how do I fine tune them with my data? Can use AutoTrain, or can use SageMaker

What about demos? Use Spaces (hosted ML apps) <- python file, Gradio, or Docker

Spaces is probably the most popular

HF lets you deploy your models
 - select cloud provider
 - select region
 - select instance type

HF has enterprise solutions
 - enterprise hub, same HF Hub with additional security and services layers
 - certified SOC2
 - SSO/SAML

HF providers expert support
 - dedicated success ML engineer
 - ongoing support and Q&A
 - any use case
 - AWS certified consulting

New: training cluster as a service
 - pretraining (we'll make your BloombergGPT), perhaps only a couple teams have built 10B+ models
 - built Bloom 175B, Starcoder 15B, Flamingo reproduction (multi-modal)

SafeCoder: on-VPC GitHub Copilot
 - uses StarCoder

SafeChat: on VPC chatGPT, custom, compliant, secure


Questions:

Released some courses on speech recognition, diffuser models, other stuff
 - building your own fine-tuned model adapters

HFs goals: allow every company to build their own AI, don't need to outsource it to third parties, and wants every company to use HF
In the short term, day to day goal is to offer great resources to the community and make them available quickly

Accessibility and transparency are the most important things
Wrong way is to pretend that you can lock it away
Promoting a vision of the future where the power to build with AI is decentralized
Maximize positive uses while minimizing harmful uses
