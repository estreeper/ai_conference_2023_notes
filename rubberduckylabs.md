Alexandra Johnson, Co-Founder and CEO Rubber Ducky Labs
September 27th, 2023

Founded 2018

90% fraud detection, lead scoring, and recommender systems

Seminal paper on collaborative filtering was published 20 years ago

Why are recommender systems important?
 - a great system is worth $$$$
 - TikTok has taught consumers to expect hyperpersonalized content = more interactions, more conversions
 - ML allows you to hyperpersonalize

Why RecSys is more than ML models
Reality: many different ML models to account for different objectives and latency concerns
Key steps: retrieval -> filtering -> scoring -> ordering

Problem: long tail of bugs

ML-systems can surface offensive or off-brand content
Hard to incoproate domain knowledge into ML models
Executives yell at 

Solution: non-ML business logic on top of ML (guardrails)

ML team overwhelmed by requests to add rules
 - can you boost this thing?

Often build a self-serve marketing boost system
 - often has 1000s of rules
 - ML model is too constrained

Problem: triaging bugs is slow
 - you can't write out test cases
 - this item is good, why aren't we showing it?
 - why did this user get recommended that item?

Solution: debug tooling for the ML system (i.e. Ariadne built by the Stitch Fix team)

Problem: diffitult to build intuition
 - hard to understand what's happening in the system
 - desire to move beyond averages
 - build arguments for what to invest in next
 - decide whether or not to launch a feature

Solution: slice and dice at scale
 - identity underperforming segment, build new feature
 - slice and dice experiment results on traditionally underperforming segments: new users, power users, geos, other sensitive facets

 Huge infrastructure challenges when building at scale

 Problem: slow iteration cycles
  - one ML team, many placements, many carousels
  - building new models/pipelines is time consuming and expensive
  - don't want to launch a new model every time this happens

Solution: recommender systems playground
 - available to engineering/product stakeholders
 - see and select available models
 - simulate recommendations
 - build into placements/carousels
