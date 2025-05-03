---
project: dia
stars: 14327
description: A TTS model capable of generating ultra-realistic dialogue in one pass.
url: https://github.com/nari-labs/dia
---

Dia is a 1.6B parameter text to speech model created by Nari Labs.

Dia **directly generates highly realistic dialogue from a transcript**. You can condition the output on audio, enabling emotion and tone control. The model can also produce nonverbal communications like laughter, coughing, clearing throat, etc.

To accelerate research, we are providing access to pretrained model checkpoints and inference code. The model weights are hosted on Hugging Face. The model only supports English generation at the moment.

We also provide a demo page comparing our model to ElevenLabs Studio and Sesame CSM-1B.

-   (Update) We have a ZeroGPU Space running! Try it now here. Thanks to the HF team for the support :)
-   Join our discord server for community support and access to new features.
-   Play with a larger version of Dia: generate fun conversations, remix content, and share with friends. 🔮 Join the waitlist for early access.

Generation Guidelines
---------------------

-   Keep input text length moderate
    -   Short input (corresponding to under 5s of audio) will sound unnatural
    -   Very long input (corresponding to over 20s of audio) will make the speech unnaturally fast.
-   Use non-verbal tags sparingly, from the list in the README. Overusing or using unlisted non-verbals may cause weird artifacts.
-   Always begin input text with `[S1]`, and always alternate between `[S1]` and `[S2]` (i.e. `[S1]`... `[S1]`... is not good)
-   When using audio prompts (voice cloning), follow these instructions carefully:
    -   Provide the transcript of the to-be cloned audio before the generation text.
    -   Transcript must use `[S1]`, `[S2]` speaker tags correctly (i.e. single speaker: `[S1]`..., two speakers: `[S1]`... `[S2]`...)
    -   Duration of the to-be cloned audio should be 5~10 seconds for the best results. (Keep in mind: 1 second ≈ 86 tokens)
-   Put `[S1]` or `[S2]` (the second-to-last speaker's tag) at the end of the audio to improve audio quality at the end

### Install via pip

# Install directly from GitHub
pip install git+https://github.com/nari-labs/dia.git

### Run the Gradio UI

This will open a Gradio UI that you can work on.

git clone https://github.com/nari-labs/dia.git
cd dia && uv run app.py

or if you do not have `uv` pre-installed:

git clone https://github.com/nari-labs/dia.git
cd dia
python -m venv .venv
source .venv/bin/activate
pip install -e .
python app.py

Note that the model was not fine-tuned on a specific voice. Hence, you will get different voices every time you run the model. You can keep speaker consistency by either adding an audio prompt (a guide coming VERY soon - try it with the second example on Gradio for now), or fixing the seed.

Features
--------

-   Generate dialogue via `[S1]` and `[S2]` tag
-   Generate non-verbal like `(laughs)`, `(coughs)`, etc.
    -   Below verbal tags will be recognized, but might result in unexpected output.
    -   `(laughs), (clears throat), (sighs), (gasps), (coughs), (singing), (sings), (mumbles), (beep), (groans), (sniffs), (claps), (screams), (inhales), (exhales), (applause), (burps), (humming), (sneezes), (chuckle), (whistles)`
-   Voice cloning. See `example/voice_clone.py` for more information.
    -   In the Hugging Face space, you can upload the audio you want to clone and place its transcript before your script. Make sure the transcript follows the required format. The model will then output only the content of your script.

⚙️ Usage
--------

### As a Python Library

from dia.model import Dia

model \= Dia.from\_pretrained("nari-labs/Dia-1.6B", compute\_dtype\="float16")

text \= "\[S1\] Dia is an open weights text to dialogue model. \[S2\] You get full control over scripts and voices. \[S1\] Wow. Amazing. (laughs) \[S2\] Try it now on Git hub or Hugging Face."

output \= model.generate(text, use\_torch\_compile\=True, verbose\=True)

model.save\_audio("simple.mp3", output)

A pypi package and a working CLI tool will be available soon.

💻 Hardware and Inference Speed
-------------------------------

Dia has been tested on only GPUs (pytorch 2.0+, CUDA 12.6). CPU support is to be added soon. The initial run will take longer as the Descript Audio Codec also needs to be downloaded.

These are the speed we benchmarked in RTX 4090.

precision

realtime factor w/ compile

realtime factor w/o compile

VRAM

`bfloat16`

x2.1

x1.5

~10GB

`float16`

x2.2

x1.3

~10GB

`float32`

x1

x0.9

~13GB

We will be adding a quantized version in the future.

If you don't have hardware available or if you want to play with bigger versions of our models, join the waitlist here.

🪪 License
----------

This project is licensed under the Apache License 2.0 - see the LICENSE file for details.

⚠️ Disclaimer
-------------

This project offers a high-fidelity speech generation model intended for research and educational use. The following uses are **strictly forbidden**:

-   **Identity Misuse**: Do not produce audio resembling real individuals without permission.
-   **Deceptive Content**: Do not use this model to generate misleading content (e.g. fake news)
-   **Illegal or Malicious Use**: Do not use this model for activities that are illegal or intended to cause harm.

By using this model, you agree to uphold relevant legal standards and ethical responsibilities. We **are not responsible** for any misuse and firmly oppose any unethical usage of this technology.

🔭 TODO / Future Work
---------------------

-   Docker support for ARM architecture and MacOS.
-   Optimize inference speed.
-   Add quantization for memory efficiency.

🤝 Contributing
---------------

We are a tiny team of 1 full-time and 1 part-time research-engineers. We are extra-welcome to any contributions! Join our Discord Server for discussions.

🤗 Acknowledgements
-------------------

-   We thank the Google TPU Research Cloud program for providing computation resources.
-   Our work was heavily inspired by SoundStorm, Parakeet, and Descript Audio Codec.
-   Hugging Face for providing the ZeroGPU Grant.
-   "Nari" is a pure Korean word for lily.
-   We thank Jason Y. for providing help with data filtering.

⭐ Star History
--------------
