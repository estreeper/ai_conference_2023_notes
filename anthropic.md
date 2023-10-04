Ben Mann cofounder Anthropic
September 27th

Aligning AI with human values
 Lessons from building Claude

Launched in July 2023 but had companies like Slack using it via API for a year

Helpful
 - concise, efficient, appropriate responses
Honest
 - express uncertainty
Harmless
 - avoid harm, don't aid bad behaviors

These can be in conflict with each other

2022: achieved a breakthrough to make it so humans didn't need to intervene - use the model itself to evaluate itself (rather than just human feedback)

Scalable oversight: realied manual moderation would not suffice.
 - automated testing: generate a diverse set of evals using the model (150 evals, 1000 examples), then use other models to filter for quality
 - expert red teaming: complements automated testing through human ingenuity, teams act as adversaries to uncover flaws/edge cases. Spent 150 hours working with experts in biology with the guardrails turned off. Models may enable tasks 
  - classifier filters, make it harder to have dangerous capabilities
 - external crowdsourcing, people flag concerning responses that automated methods miss

Deployment
 - human feedback data 2021
 - comfortable with it in 2022
 - rewrote their stack before launch to make it scalable
 - structured training data to never use user input
 - frequently see spikes of abusive content (jailbreaks) - patch the attack vector and follow up with a more comprehensive fix in 1-2 days
 - CMU 81% success in jailbreaks on OpenAI, 62% Palm2, 2% Claude

AI Safety Levels (ASLs)

ASL-1 smaller models
ASL-2 present LLMs, some dangerous capabilities but not reliable
ASL-3 significantly higher risks, will wait on this
ASL-4+ speculative

"Let's build safe AGI"
