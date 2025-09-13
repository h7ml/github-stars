---
project: ai-notes
stars: 6048
description: notes for software engineers getting up to speed on new AI developments. Serves as datastore for https://latent.space writing, and product brainstorming, but has cleaned up canonical references under the /Resources folder.
url: https://github.com/swyxio/ai-notes
---

AI Notes
========

notes on AI state of the art, with a focus on generative and large language models. These are the "raw materials" for the https://lspace.swyx.io/ newsletter.

> This repo used to be called https://github.com/sw-yx/prompt-eng, but was renamed because Prompt Engineering is Overhyped. This is now an AI Engineering notes repo.

This Readme is just the high level overview of the space; you should see the most updates in the OTHER markdown files in this repo:

-   `TEXT.md` - text generation, mostly with GPT-4
    -   `TEXT_CHAT.md` - information on ChatGPT and competitors, as well as derivative products
    -   `TEXT_SEARCH.md` - information on GPT-4 enabled semantic search and other info
    -   `TEXT_PROMPTS.md` - a small swipe file of good GPT3 prompts
-   `INFRA.md` - raw notes on AI Infrastructure, Hardware and Scaling
-   `AUDIO.md` - tracking audio/music/voice transcription + generation
-   `CODE.md` - codegen models, like Copilot
-   `IMAGE_GEN.md` - the most developed file, with the heaviest emphasis notes on Stable Diffusion, and some on midjourney and dalle.
    -   `IMAGE_PROMPTS.md` - a small swipe file of good image prompts
-   **Resources**: standing, cleaned up resources that are meant to be permalinked to
-   **stub notes** - very small/lightweight proto pages of future coverage areas - `AGENTS.md` - tracking "agentic AI"
-   **blog ideas**\- potential blog post ideas derived from these notes bc

Table of Contents

-   Motivational Use Cases
-   Top AI Reads
-   Communities
-   People
-   Misc
-   Quotes, Reality & Demotivation
-   Legal, Ethics, and Privacy

Motivational Use Cases
----------------------

-   images
    -   https://mpost.io/best-100-stable-diffusion-prompts-the-most-beautiful-ai-text-to-image-prompts
    -   3D MRI synthetic brain images - positive reception from neuroimaging statistician
    -   multiplayer stable diffusion
-   video
    -   img2img of famous movie scenes (lalaland)
        -   img2img transforming actor with ebsynth + koe\_recast
        -   how ebsynth works https://twitter.com/TomLikesRobots/status/1612047103806545923?s=20
    -   virtual fashion (karenxcheng)
    -   seamless tiling images
    -   evolution of scenes (xander)
    -   outpainting https://twitter.com/orbamsterdam/status/1568200010747068417?s=21&t=rliacnWOIjJMiS37s8qCCw
    -   webUI img2img collaboration https://twitter.com/\_akhaliq/status/1563582621757898752
    -   image to video with rotation https://twitter.com/TomLikesRobots/status/1571096804539912192
    -   "prompt paint" https://twitter.com/1littlecoder/status/1572573152974372864
    -   audio2video animation of your face https://twitter.com/siavashg/status/1597588865665363969
    -   physical toys to 3d model + animation https://twitter.com/sergeyglkn/status/1587430510988611584
    -   music videos
        -   video killed the radio star, colab This uses OpenAI's Whisper speech-to-text, allowing you to take a YouTube video & create a Stable Diffusion animation prompted by the lyrics in the YouTube video
        -   Stable Diffusion Videos generates videos by interpolating between prompts and audio
    -   direct text2video project
        -   https://twitter.com/\_akhaliq/status/1575546841533497344
        -   https://makeavideo.studio/ - explorer https://webvid.datasette.io/webvid/videos
        -   https://phenaki.video/
        -   https://github.com/THUDM/CogVideo
        -   https://imagen.research.google/video/
-   text-to-3d https://twitter.com/\_akhaliq/status/1575541930905243652
    -   https://dreamfusion3d.github.io/
    -   open source impl: https://github.com/ashawkey/stable-dreamfusion
    -   demo https://twitter.com/\_akhaliq/status/1578035919403503616
-   text products
    -   has a list of usecases at the end https://huyenchip.com/2023/04/11/llm-engineering.html
-   Jasper
-   GPT for Obsidian https://reasonabledeviations.com/2023/02/05/gpt-for-second-brain/
-   gpt3 email https://github.com/sw-yx/gpt3-email and email clustering
-   gpt3() in google sheet 2020, 2022 - sheet google sheets https://twitter.com/mehran\_\_jalali/status/1608159307513618433
    -   https://gpt3demo.com/apps/google-sheets
    -   Charm https://twitter.com/shubroski/status/1620139262925754368?s=20
-   https://www.summari.com/ Summari helps busy people read more
-   market maps/landscapes
    -   elad gil 2024 stack chart
    -   sequoia market map jan 2023, july 2023, sep 2023
    -   base10 market map https://twitter.com/letsenhance\_io/status/1594826383305449491
    -   matt shumer market map https://twitter.com/mattshumer\_/status/1620465468229451776 https://docs.google.com/document/d/1sewTBzRF087F6hFXiyeOIsGC1N4N3O7rYzijVexCgoQ/edit
    -   nfx https://www.nfx.com/post/generative-ai-tech-5-layers?ref=context-by-cohere
    -   a16z https://a16z.com/2023/01/19/who-owns-the-generative-ai-platform/
        -   https://a16z.com/2023/06/20/emerging-architectures-for-llm-applications/
        -   https://a16z.com/100-gen-ai-apps
    -   madrona https://www.madrona.com/foundation-models/
    -   coatue
        -   https://www.coatue.com/blog/perspective/ai-the-coming-revolution-2023
        -   https://x.com/Sam\_Awrabi/status/1742324900034150646?s=20
-   game assets -
    -   emad thread https://twitter.com/EMostaque/status/1591436813750906882
    -   scenario.gg https://twitter.com/emmanuel\_2m/status/1593356241283125251
    -   3d game character modeling example
    -   MarioGPT https://arxiv.org/pdf/2302.05981.pdf https://www.slashgear.com/1199870/mariogpt-uses-ai-to-generate-endless-super-mario-levels-for-free/ https://github.com/shyamsn97/mario-gpt/blob/main/mario\_gpt/level.py
    -   https://news.ycombinator.com/item?id=36295227

Top AI Reads
------------

The more advanced GPT3 reads have been split out to https://github.com/sw-yx/ai-notes/blob/main/TEXT.md

-   https://www.gwern.net/GPT-3#prompts-as-programming
-   https://learnprompting.org/

### Beginner Reads

-   Karpathy 2025 Intro to LLMs (summary)
-   Bill Gates on AI (tweet)
    -   "The development of AI is as fundamental as the creation of the microprocessor, the personal computer, the Internet, and the mobile phone. It will change the way people work, learn, travel, get health care, and communicate with each other."
-   Steve Yegge on AI for developers
-   Karpathy 2023 intro to LLMs (notes from Sarah Chieng)
-   Prompt Engineering guide from OpenAI at NeurIPS via Sarah Chieng
-   Why this AI moment might be the real deal
-   Sam Altman - Moore's Law for Everything
-   excellent introduction to foundation models from MSR https://youtu.be/HQI6O5DlyFc
-   openAI prompt tutorial https://beta.openai.com/docs/quickstart/add-some-examples
-   google LAMDA intro https://aitestkitchen.withgoogle.com/how-lamda-works
-   karpathy gradient descent course
-   FT visual storytelling on "how transformers work"
-   DALLE2 prompt writing book http://dallery.gallery/wp-content/uploads/2022/07/The-DALL%C2%B7E-2-prompt-book-v1.02.pdf
-   https://medium.com/nerd-for-tech/prompt-engineering-the-career-of-future-2fb93f90f117
-   How to use AI to do stuff across getting information, working with data, and making images
-   https://ourworldindata.org/brief-history-of-ai ai progress overview with nice charts
-   Jon Stokes' AI Content Generation, Part 1: Machine Learning Basics
-   Andrew Ng - Opportunities in AI
-   What are transformer models and how do they work? - maybe a bit too high level
-   text generation
    -   humanloop's prompt engineering 101
    -   Stephen Wolfram's explanations https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/
    -   equivalent from jon stokes jonstokes.com/p/the-chat-stack-gpt-4-and-the-near
    -   https://andymatuschak.org/prompts/
    -   cohere's LLM university https://docs.cohere.com/docs/llmu
        -   Jay alammar's guide to all the things: https://llm.university/
    -   https://www.jonstokes.com/p/chatgpt-explained-a-guide-for-normies for normies
-   image generation
    -   https://wiki.installgentoo.com/wiki/Stable\_Diffusion overview
    -   https://www.reddit.com/r/StableDiffusion/comments/x41n87/how\_to\_get\_images\_that\_dont\_suck\_a/
    -   https://mpost.io/best-100-stable-diffusion-prompts-the-most-beautiful-ai-text-to-image-prompts/
    -   https://www.kdnuggets.com/2021/03/beginners-guide-clip-model.html
    -   https://www.seangoedecke.com/diffusion-models-explained/
-   for nontechnical
    -   https://www.jonstokes.com/p/ai-content-generation-part-1-machine
    -   https://www.protocol.com/generative-ai-startup-landscape-map
    -   https://twitter.com/saranormous/status/1572791179636518913

### Intermediate Reads

-   **State of AI Report**: 2018, 2019, 2020, 2021, 2022
-   reverse chronological major events https://bleedingedge.ai/
-   What we Know about LLMs - great recap of research
-   Karpathy's 1hr guide to LLMs - summary from Sarah Chieng
    
    -   1.  What is a large language model (LLM)?
        
        -   There are two main components of an LLM
            -   What does an LLM do?
    
    1.  How do you create an LLM?
        -   Stage 1: Model Pre-Training
        -   Stage 2: Model Fine-tuning
            -   Stage 2b: \[Optional\] Additional Fine-tuning
        -   Stage 3: Model Inference
        -   Stage 4: \[Optional\] Supercharging LLMs with Customization
    2.  The Current LLM “Leaderboard”
    3.  The Future of LLMs: What’s Next?
        -   How to improve LLM performance?
            -   LLM Scaling Laws
            -   Self-Improvement
        -   How to improve LLM abilities?
            -   Multimodality
            -   System 1 + 2 Thinking
    4.  The LLM Dark Arts
        -   Jailbreaking
        -   Prompt Injecting
        -   Data Poisoning & Backdoor Attacks
    
    -   Evan Morikawa guide to LLM math especially the 5 scaling challenges piece
-   A Hacker's Guide to Language Models (youtube) Jeremy Howard's 90min complete overview of LLM learnings - starting at the basics: the 3-step pre-training / fine-tuning / classifier ULMFiT approach used in all modern LLMs.
-   https://spreadsheets-are-all-you-need.ai
-   "Catching up on the weird world of LLMs" - Simon Willison's 40min overview + Open Questions for AI Engineers
-   LLMs overview from Flyte
-   Clementine Fourrier on How Evals are Done
-   VLMs Zero to Hero (tweet)
-   Patterns for building LLM-based systems and products - great recap
    -   Evals: To measure performance
    -   RAG: To add recent, external knowledge
    -   Fine-tuning: To get better at specific tasks
    -   Caching: To reduce latency & cost
    -   Guardrails: To ensure output quality
    -   Defensive UX: To anticipate & manage errors gracefully
    -   Collect user feedback: To build our data flywheel
-   Vector Databases: A Technical Primer \[pdf\] very nice slides on Vector DBs
    -   Missing coverage of hybrid search (vector + lexical). Further discussions
-   Visual introduction to ML
-   A16z AI Canon https://a16z.com/2023/05/25/ai-canon/
    -   **Software 2.0**: Andrej Karpathy was one of the first to clearly explain (in 2017!) why the new AI wave really matters. His argument is that AI is a new and powerful way to program computers. As LLMs have improved rapidly, this thesis has proven prescient, and it gives a good mental model for how the AI market may progress.
    -   **State of GPT**: Also from Karpathy, this is a very approachable explanation of how ChatGPT / GPT models in general work, how to use them, and what directions R&D may take.
    -   **What is ChatGPT doing … and why does it work?**: Computer scientist and entrepreneur Stephen Wolfram gives a long but highly readable explanation, from first principles, of how modern AI models work. He follows the timeline from early neural nets to today’s LLMs and ChatGPT.
    -   **Transformers, explained**: This post by Dale Markowitz is a shorter, more direct answer to the question “what is an LLM, and how does it work?” This is a great way to ease into the topic and develop intuition for the technology. It was written about GPT-3 but still applies to newer models.
    -   **How Stable Diffusion works**: This is the computer vision analogue to the last post. Chris McCormick gives a layperson’s explanation of how Stable Diffusion works and develops intuition around text-to-image models generally. For an even _gentler_ introduction, check out this comic from r/StableDiffusion.
        -   (2025) 3blue1brown on how diffusion works
    -   Explainers
        -   **Deep learning in a nutshell: core concepts**: This four-part series from Nvidia walks through the basics of deep learning as practiced in 2015, and is a good resource for anyone just learning about AI.
        -   **Practical deep learning for coders**: Comprehensive, free course on the fundamentals of AI, explained through practical examples and code.
        -   **Word2vec explained**: Easy introduction to embeddings and tokens, which are building blocks of LLMs (and all language models).
            -   https://news.ycombinator.com/item?id=44708028
        -   **Yes you should understand backprop**: More in-depth post on back-propagation if you want to understand the details. If you want even more, try the Stanford CS231n lecture (course here) on Youtube.
    -   Courses
        -   **Stanford CS229**: Introduction to Machine Learning with Andrew Ng, covering the fundamentals of machine learning.
        -   **Stanford CS224N**: NLP with Deep Learning with Chris Manning, covering NLP basics through the first generation of LLMs.
-   https://github.com/mlabonne/llm-course
-   https://cims.nyu.edu/~sbowman/eightthings.pdf
    1.  LLMs predictably get more capable with increasing investment, even without targeted innovation.
    2.  Many important LLM behaviors emerge unpredictably as a byproduct of increasing investment.
    3.  LLMs often appear to learn and use representations of the outside world.
    4.  There are no reliable techniques for steering the behavior of LLMs.
    5.  Experts are not yet able to interpret the inner workings of LLMs.
    6.  Human performance on a task isn’t an upper bound on LLM performance.
    7.  LLMs need not express the values of their creators nor the values encoded in web text.
    8.  Brief interactions with LLMs are often misleading.
    9.  simonw highlights https://fedi.simonwillison.net/@simon/110144185463887790
-   10 open challenges in LLM research https://huyenchip.com/2023/08/16/llm-research-open-challenges.html
-   openai prompt eng cookbook https://github.com/openai/openai-cookbook/blob/main/techniques\_to\_improve\_reliability.md
-   on prompt eng overview https://lilianweng.github.io/posts/2023-03-15-prompt-engineering/
-   https://moultano.wordpress.com/2023/06/28/the-many-ways-that-digital-minds-can-know/ comparing search vs ai
-   Recap of 2022's major AI developments https://www.deeplearning.ai/the-batch/issue-176/
-   DALLE2 asset generation + inpainting https://twitter.com/aifunhouse/status/1576202480936886273?s=20&t=5EXa1uYDPVa2SjZM-SxhCQ
-   suhail journey https://twitter.com/Suhail/status/1541276314485018625?s=20&t=X2MVKQKhDR28iz3VZEEO8w
-   composable diffusion - "AND" instead of "and" https://twitter.com/TomLikesRobots/status/1580293860902985728
-   on BPE tokenization https://towardsdatascience.com/byte-pair-encoding-subword-based-tokenization-algorithm-77828a70bee0 see also google sentencepiece and openai tiktoken
    -   see visualization here https://lucalp.dev/bitter-lesson-tokenization-and-blt/
    -   source in GPT2 source https://github.com/openai/gpt-2/blob/master/src/encoder.py
    -   note that BPEs are suboptimal https://www.lesswrong.com/posts/dFbfCLZA4pejckeKc/a-mechanistic-explanation-for-solidgoldmagikarp-like-tokens?commentId=9jNdKscwEWBB4GTCQ
        -   //---------------------------------------------------------------------------------------------------------------- is a single GPT-4 token
        -   GPT-3.5 crashes when it thinks about useRalativeImagePath too much
        -   causes math and string character issues https://news.ycombinator.com/item?id=35363769
        -   and cause issues with evals
        -   glitch tokens happen when tokenizer has different dataset than LLM
        -   karpathy talking about why tokenization is messy
    -   https://platform.openai.com/tokenizer and https://github.com/openai/tiktoken (more up to date: https://tiktokenizer.vercel.app/)
    -   Wordpiece -> BPE -> SentenceTransformer
        -   Preliminary reading on Embeddings
        -   https://youtu.be/QdDoFfkVkcw?si=qefZSDDSpxDNd313
        -   Huggingface MTEB Benchmark of a bunch of Embeddings
        -   notable issues with GPT3 Embeddings and alternatives to consider
    -   https://observablehq.com/@simonw/gpt-3-token-encoder-decoder
    -   karpathy wants tokenization to go away https://twitter.com/karpathy/status/1657949234535211009
    -   positional encoding not needed for decoder only https://twitter.com/a\_kazemnejad/status/1664277559968927744?s=20
-   creates its own language https://twitter.com/giannis\_daras/status/1531693104821985280
-   Google Cloud Generative AI Learning Path https://www.cloudskillsboost.google/paths/118
-   img2img https://andys.page/posts/how-to-draw/
-   on language modeling https://lena-voita.github.io/nlp\_course/language\_modeling.html and approachable but technical explanation of language generation including sampling from distributions and some mechanistic intepretability (finding neuron that tracks quote state)
-   quest for photorealism https://www.reddit.com/r/StableDiffusion/comments/x9zmjd/quest\_for\_ultimate\_photorealism\_part\_2\_colors/
    -   https://medium.com/merzazine/prompt-design-for-dall-e-photorealism-emulating-reality-6f478df6f186
-   settings tweaking https://www.reddit.com/r/StableDiffusion/comments/x3k79h/the\_feeling\_of\_discovery\_sd\_is\_like\_a\_great\_proc/
    -   seed selection https://www.reddit.com/r/StableDiffusion/comments/x8szj9/tutorial\_seed\_selection\_and\_the\_impact\_on\_your/
    -   minor parameter parameter difference study (steps, clamp\_max, ETA, cutn\_batches, etc) https://twitter.com/KyrickYoung/status/1500196286930292742
    -   Generative AI: Autocomplete for everything https://noahpinion.substack.com/p/generative-ai-autocomplete-for-everything?sd=pf
    -   How does GPT Obtain its Ability? Tracing Emergent Abilities of Language Models to their Sources good paper with the development history of the GPT family of models and how the capabilities developed
-   https://barryz-architecture-of-agentic-llm.notion.site/Almost-Everything-I-know-about-LLMs-d117ca25d4624199be07e9b0ab356a77

### Advanced Reads

-   https://github.com/Mooler0410/LLMsPracticalGuide
    -   good curated list of all the impt papers
-   https://github.com/eleutherAI/cookbook#the-cookbook Eleuther AI's list of resources for training. compare to https://github.com/google-research/tuning\_playbook
-   anti hype LLM reading list https://gist.github.com/veekaybee/be375ab33085102f9027853128dc5f0e
-   6 papers from Jason Wei of OpenAI (blog)
    -   GPT-3 paper (https://arxiv.org/abs/2005.14165)
    -   chain-of-thought prompting (https://arxiv.org/abs/2201.11903)
    -   scaling laws, (https://arxiv.org/abs/2001.08361)
    -   emergent abilities (https://arxiv.org/abs/2206.07682)
    -   language models can follow both flipped labels and semantically-unrelated labels (https://arxiv.org/abs/2303.03846)
-   LLM Paper Notes - notes from the Latent Space paper club by Eugene Yan
-   CMU LLM syllabus
-   explaining batching in inference relevant to DeepSeek R1
-   Transformers from scratch https://e2eml.school/transformers.html
    -   transformers vs LSTM https://medium.com/analytics-vidhya/why-are-lstms-struggling-to-matchup-with-transformers-a1cc5b2557e3
    -   transformer code walkthru https://twitter.com/mark\_riedl/status/1555188022534176768
    -   transformer familyi https://lilianweng.github.io/posts/2023-01-27-the-transformer-family-v2/
        -   carmack paper list https://news.ycombinator.com/item?id=34639634
        -   Transformer models: an introduction and catalog https://arxiv.org/abs/2302.07730
        -   Deepmind - formal algorithms for transformers https://arxiv.org/pdf/2207.09238.pdf
    -   Jay Alammar explainers
        -   https://jalammar.github.io/illustrated-transformer/
        -   https://jalammar.github.io/visualizing-neural-machine-translation-mechanics-of-seq2seq-models-with-attention/
-   karpathy on transformers
    -   **Convergence**: The ongoing consolidation in AI is incredible. When I started ~decade ago vision, speech, natural language, reinforcement learning, etc. were completely separate; You couldn't read papers across areas - the approaches were completely different, often not even ML based. In 2010s all of these areas started to transition 1) to machine learning and specifically 2) neural nets. The architectures were diverse but at least the papers started to read more similar, all of them utilizing large datasets and optimizing neural nets. But as of approx. last two years, even the neural net architectures across all areas are starting to look identical - a Transformer (definable in ~200 lines of PyTorch https://github.com/karpathy/minGPT/blob/master/mingpt/model.py…), with very minor differences. Either as a strong baseline or (often) state of the art. (tweetstorm)
    -   **Why Transformers won**: The Transformer is a magnificient neural network architecture because it is a general-purpose differentiable computer. It is simultaneously: 1) expressive (in the forward pass) 2) optimizable (via backpropagation+gradient descent) 3) efficient (high parallelism compute graph) tweetstorm
        -   https://twitter.com/karpathy/status/1593417989830848512?s=20
        -   elaborated in 1hr stanford lecture and 8min lex fridman summary
    -   BabyGPT with two tokens 0/1 and context length of 3, viewing it as a finite state markov chain. It was trained on the sequence "111101111011110" for 50 iterations. The parameters and the architecture of the Transformer modifies the probabilities on the arrows.
    -   Build GPT from scratch https://www.youtube.com/watch?v=kCc8FmEb1nY
    -   different GPT from scratch in 60 LOC https://jaykmody.com/blog/gpt-from-scratch/
-   Diffusion models from scratch, from a new theoretical perspective - code driven intro of diffusion models
-   137 emergent abilities of large language models
    -   Emergent few-shot prompted tasks: BIG-Bench and MMLU benchmarks
    -   Emergent prompting strategies
        -   Instruction-following
        -   Scratchpad
        -   Using open-book knowledge for fact checking
        -   Chain-of-thought prompting
        -   Differentiable search index
        -   Self-consistency
        -   Leveraging explanations in prompting
        -   Least-to-most prompting
        -   Zero-shot chain-of-thought
        -   Calibration via P(True)
        -   Multilingual chain-of-thought
        -   Ask-me-anything prompting
    -   some pushback - are they a mirage? just dont use harsh metrics
        -   https://www.jasonwei.net/blog/common-arguments-regarding-emergent-abilities
        -   https://hai.stanford.edu/news/ais-ostensible-emergent-abilities-are-mirage
    -   Images
        -   Eugene Yan explanation of the Text to Image stack https://eugeneyan.com/writing/text-to-image/
        -   VQGAN/CLIP https://minimaxir.com/2021/08/vqgan-clip/
        -   10 years of Image generation history https://zentralwerkstatt.org/blog/ten-years-of-image-synthesis
        -   Vision Transformers (ViT) Explained https://www.pinecone.io/learn/vision-transformers/
    -   negative prompting https://minimaxir.com/2022/11/stable-diffusion-negative-prompt/
    -   best papers of 2022 https://www.yitay.net/blog/2022-best-nlp-papers
    -   Predictability and Surprise in Large Generative Models - good survey paper of what we know about scaling and capabilities and rise of LLMs so far
-   more prompt eng papers https://github.com/dair-ai/Prompt-Engineering-Guide
-   https://creator.nightcafe.studio/vqgan-clip-keyword-modifier-comparison VQGAN+CLIP Keyword Modifier Comparison
-   History of Transformers
    -   richard socher on their contribution to attention mechanism leading up to transformers https://overcast.fm/+r1P4nKfFU/1:00:00
    -   https://kipp.ly/blog/transformer-taxonomy/ This document is my running literature review for people trying to catch up on AI. It covers 22 models, 11 architectural changes, 7 post-pre-training techniques and 3 training techniques (and 5 things that are none of the above)
    -   Understanding Large Language Models A Cross-Section of the Most Relevant Literature To Get Up to Speed
        -   giving credit to Bandanau et al (2014), which I believe first proposed the concept of applying a Softmax function over token scores to compute attention, setting the stage for the original transformer by Vaswani et al (2017). https://news.ycombinator.com/item?id=35589756
    -   https://finbarrtimbers.substack.com/p/five-years-of-progress-in-gpts GPT1/2/3, Megatron, Gopher, Chinchilla, PaLM, LLaMa
    -   good summary paper (8 things to know) https://cims.nyu.edu/~sbowman/eightthings.pdf
-   Huggingface MOE explainer
-   https://blog.alexalemi.com/kl-is-all-you-need.html

We compared 126 keyword modifiers with the same prompt and initial image. These are the results.

-   https://creator.nightcafe.studio/collection/8dMYgKm1eVXG7z9pV23W
-   Google released PartiPrompts as a benchmark: https://parti.research.google/ "PartiPrompts (P2) is a rich set of over 1600 prompts in English that we release as part of this work. P2 can be used to measure model capabilities across various categories and challenge aspects."
-   Video tutorials
    -   Pixel art https://www.youtube.com/watch?v=UvJkQPtr-8s&feature=youtu.be
-   History of papers
    -   2008: Unified Architecture for NLP (Collobert-Weston) https://twitter.com/ylecun/status/1611921657802768384
    -   2015: Semi-supervised sequence learning https://twitter.com/deliprao/status/1611896130589057025?s=20
    -   2017: Transformers (Vaswani et al)
    -   2018: GPT (Radford et al)
    
-   Misc
    -   StabilityAI CIO perspective https://danieljeffries.substack.com/p/the-turning-point-for-truly-open?sd=pf
    -   https://github.com/awesome-stable-diffusion/awesome-stable-diffusion
    -   https://github.com/microsoft/LMOps guide to msft prompt research
    -   gwern's behind the scenes discussion of Bing, GPT4, and the Microsoft-OpenAI relationship https://www.lesswrong.com/posts/jtoPawEhLNXNxvgTT/bing-chat-is-blatantly-aggressively-misaligned

### other lists like this

-   https://gist.github.com/rain-1/eebd5e5eb2784feecf450324e3341c8d
-   https://github.com/underlines/awesome-marketing-datascience/blob/master/awesome-ai.md#llama-models
-   https://github.com/imaurer/awesome-decentralized-llm

Communities
-----------

-   Discords (see https://buttondown.email/ainews for daily email recaps, updated live)
    -   Latent Space Discord (ours!)
    -   General hacking and learning
        -   ChatGPT Hackers Discord
        -   Alignment Lab AI Discord
        -   Nous Research Discord
        -   DiscoLM Discord
        -   Karpathy Discord (inactive)
        -   HuggingFace Discord
        -   Skunkworks AI Discord (new)
        -   Jeff Wang/LLM Perf enthusiasts discord
        -   CUDA Mode (Mark Saroufim) see Youtube and GitHub
    -   Art
        -   StableDiffusion Discord
        -   Deforum Discord https://discord.gg/upmXXsrwZc
        -   Lexica Discord https://discord.com/invite/bMHBjJ9wRh
    -   AI research
        -   LAION discord https://discord.gg/xBPBXfcFHd
        -   Eleuther discord: https://www.eleuther.ai/get-involved/ (primer)
    -   Various startups
        -   Perplexity Discord https://discord.com/invite/kWJZsxPDuX
        -   Midjourney's discord
            -   how to use midjourney v4 https://twitter.com/fabianstelzer/status/1588856386540417024?s=20&t=PlgLuGAEEds9HwfegVRrpg
-   https://stablehorde.net/
    -   Agents
        -   AutoGPT discord
        -   BabyAGI discord
-   Reddit
    -   https://reddit.com/r/stableDiffusion
    -   https://www.reddit.com/r/LocalLLaMA/
    -   https://www.reddit.com/r/bing
    -   https://www.reddit.com/r/openai

People
------

> \*Unknown to many people, a growing amount of alpha is now outside of Arxiv, sources include but are not limited to: https://github.com/trending, HN, that niche Discord server, anime profile picture anons on X, reddit \*- K

This list will be out of date but will get you started. My live list of people to follow is at: https://twitter.com/i/lists/1585430245762441216

-   Researchers/Developers
    -   https://twitter.com/\_jasonwei
    -   https://twitter.com/johnowhitaker/status/1565710033463156739
    -   https://twitter.com/altryne/status/1564671546341425157
    -   https://twitter.com/SchmidhuberAI
    -   https://twitter.com/nearcyan
    -   https://twitter.com/karinanguyen\_
    -   https://twitter.com/abhi\_venigalla
    -   https://twitter.com/advadnoun
    -   https://twitter.com/polynoamial
    -   https://twitter.com/vovahimself
    -   https://twitter.com/sarahookr
    -   https://twitter.com/shaneguML
    -   https://twitter.com/MaartenSap
    -   https://twitter.com/ethanCaballero
    -   https://twitter.com/ShayneRedford
    -   https://twitter.com/seb\_ruder
    -   https://twitter.com/rasbt
    -   https://twitter.com/wightmanr
    -   https://twitter.com/GaryMarcus
    -   https://twitter.com/ylecun
    -   https://twitter.com/karpathy
    -   https://twitter.com/pirroh
    -   https://twitter.com/eerac
    -   https://twitter.com/teknium
    -   https://twitter.com/alignment\_lab
    -   https://twitter.com/picocreator
    -   https://twitter.com/charlespacker
    -   https://twitter.com/ldjconfirmed
    -   https://twitter.com/nisten
    -   https://twitter.com/far\_\_el
    -   https://twitter.com/i/lists/1713824630241202630
-   News/Aggregators
    -   https://twitter.com/ai\_\_pub
    -   https://twitter.com/WeirdStableAI
    -   https://twitter.com/multimodalart
    -   https://twitter.com/LastWeekinAI
    -   https://twitter.com/paperswithcode
    -   https://twitter.com/DeepLearningAI\_
    -   https://twitter.com/dl\_weekly
    -   https://twitter.com/slashML
    -   https://twitter.com/\_akhaliq
    -   https://twitter.com/aaditya\_ai
    -   https://twitter.com/bentossell
    -   https://twitter.com/johnvmcdonnell
-   Founders/Builders/VCs
    -   https://twitter.com/levelsio
    -   https://twitter.com/goodside
    -   https://twitter.com/c\_valenzuelab
    -   https://twitter.com/Raza\_Habib496
    -   https://twitter.com/sharifshameem/status/1562455690714775552
    -   https://twitter.com/genekogan/status/1555184488606564353
    -   https://twitter.com/levelsio/status/1566069427501764613?s=20&t=camPsWtMHdSSEHqWd0K7Ig
    -   https://twitter.com/amanrsanger
    -   https://twitter.com/ctjlewis
    -   https://twitter.com/sarahcat21
    -   https://twitter.com/jackclarkSF
    -   https://twitter.com/alexandr\_wang
    -   https://twitter.com/rameerez
    -   https://twitter.com/scottastevenson
    -   https://twitter.com/denisyarats
-   Stability
    -   https://twitter.com/StabilityAI
    -   https://twitter.com/StableDiffusion
    -   https://twitter.com/hardmaru
    -   https://twitter.com/JJitsev
-   OpenAI
    -   https://twitter.com/sama
    -   https://twitter.com/ilyasut
    -   https://twitter.com/miramurati
-   HuggingFace
    -   https://twitter.com/younesbelkada
-   Artists
    -   https://twitter.com/karenxcheng/status/1564626773001719813
    -   https://twitter.com/TomLikesRobots
-   Other
    -   Companies
        -   https://twitter.com/AnthropicAI
        -   https://twitter.com/AssemblyAI
        -   https://twitter.com/CohereAI
        -   https://twitter.com/MosaicML
        -   https://twitter.com/MetaAI
        -   https://twitter.com/DeepMind
        -   https://twitter.com/HelloPaperspace
-   Bots and Apps
    -   https://twitter.com/dreamtweetapp
    -   https://twitter.com/aiarteveryhour

Quotes, Reality & Demotivation
------------------------------

-   Narrow, tedium domain usecases https://twitter.com/WillManidis/status/1584900092615528448 and https://twitter.com/WillManidis/status/1584900100480192516
-   antihype https://twitter.com/alexandr\_wang/status/1573302977418387457
-   antihype https://twitter.com/fchollet/status/1612142423425138688?s=46&t=pLCNW9pF-co4bn08QQVaUg
-   prompt eng memes
    -   https://twitter.com/\_jasonwei/status/1516844920367054848
-   things stablediffusion struggles with https://opguides.info/posts/aiartpanic/
-   New Google
    -   https://twitter.com/alexandr\_wang/status/1585022891594510336
-   New Powerpoint
-   via emad
-   Appending prompts by default in UI
-   DALLE: https://twitter.com/levelsio/status/1588588688115912705?s=20&t=0ojpGmH9k6MiEDyVG2I6gg
-   There have been two previous winters, one 1974-1980 and one 1987-1993. https://www.erichgrunewald.com/posts/the-prospect-of-an-ai-winter/. bit more commentary here. related - AI Effect - "once it works its not AI"
-   It's just matrix multiplication/stochastic parrots
    -   Even LLM skeptic Yann LeCun says LLMs have some level of understanding: https://twitter.com/ylecun/status/1667947166764023808
    -   Gary Marcus’ “Deep Learning is Hitting a Wall” https://nautil.us/deep-learning-is-hitting-a-wall-238440/ pushed symbolic systems
-   "guo lai ren" antihypers-> worriers
    -   https://adamkarvonen.github.io/machine\_learning/2024/03/20/chess-gpt-interventions.html#next-token-predictors

Legal, Ethics, and Privacy
--------------------------

-   NSFW filter https://vickiboykis.com/2022/11/18/some-notes-on-the-stable-diffusion-safety-filter/
-   On "AI Art Panic" https://opguides.info/posts/aiartpanic/
    -   I lost everything that made me love my job through Midjourney
    -   Midjourney artist list
-   Yannick influencing OPENRAIL-M https://www.youtube.com/watch?v=W5M-dvzpzSQ
-   art schools accepting AI art https://twitter.com/DaveRogenmoser/status/1597746558145265664
-   DRM issues https://undeleted.ronsor.com/voice.ai-gpl-violations-with-a-side-of-drm/
-   stealing art https://stablediffusionlitigation.com
    -   http://www.stablediffusionfrivolous.com/
    -   stable attribution https://news.ycombinator.com/item?id=34670136
    -   coutner argument for disney https://twitter.com/jonst0kes/status/1616219435492163584?s=46&t=HqQqDH1yEwhWUSQxYTmF8w
    -   research on stable diffusion copying https://twitter.com/officialzhvng/status/1620535905298817024?s=20&t=NC-nW7pfDa8nyRD08Lx1Nw This paper used Stable Diffusion to generate 175 million images over 350,000 prompts and only found 109 near copies of training data. Am I right that my main takeaway from this is how good Stable Diffusion is at _not_ memorizing training examples?
-   scraping content
    -   https://blog.ericgoldman.org/archives/2023/08/web-scraping-for-me-but-not-for-thee-guest-blog-post.htm
    -   sarah silverman case - openai response https://arstechnica.com/tech-policy/2023/08/openai-disputes-authors-claims-that-every-chatgpt-response-is-a-derivative-work/
    -   openai response
-   Licensing
    -   AI weights are not open "source" - Sid Sijbrandij
-   Diversity and Equity
    -   sexualizing minorities https://twitter.com/lanadenina/status/1680238883206832129 the reason is porn is good at bodies
    -   OpenAI tacking on "black" randomly to make DallE diverse
-   Privacy - confidential computing https://www.edgeless.systems/blog/how-confidential-computing-and-ai-fit-together/
-   AI taking jobs https://donaldclarkplanb.blogspot.com/2024/02/this-is-why-idea-that-ai-will-just.html

Alignment, Safety
-----------------

-   Anthropic - https://arxiv.org/pdf/2112.00861.pdf
    -   Helpful: attempt to do what is ask. concise, efficient. ask followups. redirect bad questions.
    -   Honest: give accurate information, express uncertainty. don't imitate responses expected from an expert if it doesn't have the capabilities/knowledge
    -   Harmless: not offensive/discriminatory. refuse to assist dangerous acts. recognize when providing sensitive/consequential advice
    -   criticism and boundaries as future direction https://twitter.com/davidad/status/1628489924235206657?s=46&t=TPVwcoqO8qkc7MuaWiNcnw
-   Just Eliezer entire body of work
    -   https://twitter.com/esyudkowsky/status/1625922986590212096
    -   agi list of lethalities https://www.lesswrong.com/posts/uMQ3cqWDPHhjtiesc/agi-ruin-a-list-of-lethalities
    -   note that eliezer has made controversial comments in the past and also in recent times (TIME article)
-   Connor Leahy may be a more sane/measured/technically competent version of yud https://overcast.fm/+aYlOEqTJ0
    -   it's not just paperclip factories
    -   https://www.lesswrong.com/posts/HBxe6wdjxK239zajf/what-failure-looks-like
-   the 6 month pause letter
    -   https://futureoflife.org/open-letter/pause-giant-ai-experiments/
    -   yann lecun vs andrew ng https://www.youtube.com/watch?v=BY9KV8uCtj4
    -   https://scottaaronson.blog/?p=7174
    -   emily bender response
    -   Geoffrey Hinton leaving Google
    -   followed up by one sentence public letter https://www.nytimes.com/2023/05/30/technology/ai-threat-warning.html
-   xrisk - Is avoiding extinction from AI really an urgent priority? (link) 
    -   AI Is not an arms race. (link) 
    -   If we’re going to label AI an ‘extinction risk,’ we need to clarify how it could happen. (link)
-   OpenAI superalignment https://www.youtube.com/watch?v=ZP\_N4q5U3eE

### regulation

-   chinese regulation https://www.chinalawtranslate.com/en/overview-of-draft-measures-on-generative-ai/
    -   https://twitter.com/mmitchell\_ai/status/1647697067006111745?s=46&t=90xQ8sGy63D2OtiaoGJuww
    -   China is the only major world power that explicitly regulates generative AI
-   italy banning chatgpt
-   -   At its annual meeting in Japan, the Group of Seven (G7), an informal bloc of industrialized democratic governments, announced the Hiroshima Process, an intergovernmental task force empowered to investigate risks of generative AI. G7 members, which include Canada, France, Germany, Italy, Japan, the United Kingdom, and the United States, vowed to craft mutually compatible laws and regulate AI according to democratic values. These include fairness, accountability, transparency, safety, data privacy, protection from abuse, and respect for human rights.
-   U.S. President Joe Biden issued a strategic plan for AI. The initiative calls on U.S. regulatory agencies to develop public datasets, benchmarks, and standards for training, measuring, and evaluating AI systems.
-   Earlier this month, France’s data privacy regulator announced a framework for regulating generative AI.
-   regulation vs Xrisk https://1a3orn.com/sub/essays-regulation-stories.html
-   Multimodal Prompt Injection in GPT4V

Misc
----

-   Whisper
    -   https://huggingface.co/spaces/sensahin/YouWhisper YouWhisper converts Youtube videos to text using openai/whisper.
    -   https://twitter.com/jeffistyping/status/1573145140205846528 youtube whipserer
    -   multilingual subtitles https://twitter.com/1littlecoder/status/1573030143848722433
    -   video subtitles https://twitter.com/m1guelpf/status/1574929980207034375
    -   you can join whisper to stable diffusion for reasons https://twitter.com/fffiloni/status/1573733520765247488/photo/1
    -   known problems https://twitter.com/lunixbochs/status/1574848899897884672 (edge case with catastrophic failures)
-   textually guided audio https://twitter.com/FelixKreuk/status/1575846953333579776
-   Codegen
    -   CodegeeX https://twitter.com/thukeg/status/1572218413694726144
    -   https://github.com/salesforce/CodeGen https://joel.tools/codegen/
-   pdf to structured data - Impira used t to do it (dead link: https://www.impira.com/blog/hey-machine-whats-my-invoice-total) but if you look hard enough on twitter there are some alternatives
-   text to Human Motion diffusion https://twitter.com/GuyTvt/status/1577947409551851520
    -   abs: https://arxiv.org/abs/2209.14916
    -   project page: https://guytevet.github.io/mdm-page/
