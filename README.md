# Text-to-Image Generation with Stable Diffusion (Practical No-05)

Practical No-05, MIT Academy of Engineering.

**Name:**
- Sanskar Ramesh Meharkar (<your 202401110029>)

## About
This project uses the pretrained Stable Diffusion model (`segmind/tiny-sd`) from the Hugging Face Diffusers library to generate images from text prompts. It studies how three settings change the quality of the generated images:

- Number of inference steps
- Guidance scale
- Sampling method (scheduler): PNDM, DDIM, Euler, Euler Ancestral, DPM-Solver++

Prompt detail and negative prompts are also tested. A fixed seed is used, so only one setting changes at a time.

## Results

| Setting | Values tested | Finding |
|---|---|---|
| Inference steps | 5, 10, 25, 50 | Quality stops improving after about 25 steps. Time doubles from 2.2 s to 4.3 s for 50 steps. |
| Guidance scale | 1, 4, 7.5, 12, 20 | Best at about 7 to 12. 1 ignores the prompt and 20 looks over-saturated. |
| Scheduler | 5 samplers | DDIM, Euler and DPM++ are clean at 10 steps. PNDM is noisy. Euler-A changes with the step count. |

- A medium guidance scale (7.5) with about 25 steps gives the best result.
- Detailed prompts give more control, and a negative prompt gives cleaner images.
- CLIP score did not follow visual quality, so it should be used with visual inspection.

## Run it
1. Open the notebook in Google Colab: [Open in Colab](https://colab.research.google.com/drive/1_680LeXxNk9g3YrU8bXJeuDEHPTEDFMW?usp=sharing)
2. Set the runtime to GPU (Runtime > Change runtime type > T4 GPU).
3. Choose Runtime > Run all (about 5 minutes).

## Files
- `pract5_genai_Sanskar_Meharkar.ipynb`: code and outputs
- `Practical_No-05_Sanskar_Meharkar.pdf`: full report

## Tools
Python, PyTorch, Hugging Face Diffusers, Google Colab.
AI assistance: Claude (used for explanations, debugging and report writing).
