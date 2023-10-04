Fran Bell CTO BP
September 27th, 2023

Lab 42: lead by Justin Lewis (Google, Tesla, 450 patents)

Focused on:
 - front-line worker safety

Myrge: code reviews as a service (human code reviewers plus AI)
 - improve code volocity

EV charging: provide recommendations of where to place them
Predictive maintenance
IoT devices for things like leak detection

Code Quality
 - "code is read more than it is written"
 - make it easy for 
Tech Debt
 - 20-40% of dev time is bogged down due to this
Cycle Times
 - how long does it take to create/release a feature?
 - more frequent, smaller changes -> lower risk

It takes ~1 day per review (which costs years at scale)

Myrge: provides code reviews as a service

Start code reviews within 15 minutes of a PR
integrated with Github
also adds comments
Myrge teams also do code reviews, building tech to get context very quickly (including documentation)
 - combine human-powered reviews with Gen AI

How do the Myrge teams get context needed to review other teams' code?
 - route the PR to the most appropriate code reviewer at hand (using ML models)
 - make sure only the code that matters is reviewed (automatically assess other parts)
 - tools to quickly review code
   - provide explanations about what is in the PR and what's happening
   - summarization/explanation
   - detect issues and make suggested fixes
   - write the reviews using AI completions
   - intelligent search across the codebase or external info like documentation

 Why not hand everything off to AI and do code reviews?
  - AI is not a silver bullet

 Shortcomings:
  - unknown unknowns: new tech, libraries, domain concepts
  - hallucinations, which undermines trust
  - context windows are too small

 AI augments vs replaces reviewers

 Humans
  - nullify hallucinations
  - enrich training data

 Myrge
  - 1 reviewer to 175 developers (typical is 1:10)
  - 5x improvement in code merge time
  - software engineers no longer have to do CR, which makes happier devs

Sami Khan sami.khan2@bp.com
Chris Gell christopher.gell@bp.com
Jasper Lyons jasper.lyons@bp.com
