Yishay Carmiel, CEO Meaning
September 27th, 2023

Can take any type of voice/accent and convert it into a target speaker

Analysis -> Synthesis

Why should we care about voice?
 - speech recognition: to understand what we're saying
 - speech synthesis (TTS): for us to understand what a machine is saying

Videos, games, new types of music
 - generating new voice content for games

MusicLM: insert music you like it will generate more

Speech recognition
Speech profiling: i.e. speaker recognition, emoiton detecion, age estimation, language recognition
Speech synthesis: generate new types of speech

Generative AI for speech

Prompt TTS: "say this in Barack Obama's voice when he's sad"
Speech -> speech (voice conversion)
Text + speech (style transfer)
Text + music: music generation
Speech => music + speech

TTS Block diagram

TTS NLU
My email is abc@gmail.com -> My e mail is a b c at g mail dot com
Please press 1939 ("one nine three nine")
It costs $1939 ("one thousand nine hundred thirty nine")

TTS Speech Generation: VITS (state of the art end to end text to speech)
Linguistic encoder: Phoneme encoder
Posterical encoder: encode audo into hiddden representation
Duration predictor and alignment search

Can clone someone's voice and have it sound very natural

State of the art of TTS

Avatar Dubbing, Podcast
Voice inpainting, editing
Video dubbing with lib sync

Under development (18-24 months will be solved): conversational speech, high expressiveness, emotion controllability

Speech to speech: don't go through the word space (creates latency)
Source -> voice fingerprint extractor -> fingerprint transformer -> voice generator -> target

Example: Meta VoiceBox

Multi-speaker TTS: ability to adapt to new speakers
 - Multi-lingual support
 - Style transfer
 - Editing and noise removal

LLM in speech

HuBERT: BERT-like LM for speech (Meta AI Blog)

Voice compression metrics: MUSHRA (how quality it is for human ear)
Can now have 10x fewer bits with almost SoTA MUSHRA

Ethics and Safety
VALL-E: can clone your voice in only 5s
VALL-E X: does not have to be in English

Audio fake detection
 - risk factors: enterprise vs consumer, consumers are not very well protected, but someone pretended to be a CTO and stole $35 million by calling CEO
 - understand the attack vectors: which voice cloning software will be used
 - need to generate suitable datasets
 building proper classifiers and detectors (synthetic versus real)
 - user specific models to add another layer of protection

 info@meaning.team

 Questions

 250ms is the current industry standard
 RT translation is hard because sometimes you need to wait until the user has ended the sentence, because word order is different
 
 Enterprises are concerned about things going sideways
 There's a huge difference between a demo and a product

