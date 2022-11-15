---
inference: true
language:
  - en
tags:
  - stable-diffusion
  - text-to-image
license: creativeml-openrail-m
---

# Stable Diffusion fine tuned on Midjourney v4 images, by [PromptHero](https://prompthero.com/)

Use prompt: 'mdjrny-v4 style'

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1vkuxKKeSYNYI2OLZm8mR-WqcokQtSURM?usp=sharing)

### Stable Diffusion v1.5 vs Midjourney v4 Diffusion 
(Same parameters, just added "mdjrny-v4 style" at the beginning):
<img src="https://s3.amazonaws.com/moonup/production/uploads/1667904587642-63265d019f9d19bfd4f45031.png" width="100%"/>
<img src="https://s3.amazonaws.com/moonup/production/uploads/1667904587623-63265d019f9d19bfd4f45031.png" width="100%"/>
<img src="https://s3.amazonaws.com/moonup/production/uploads/1667904587609-63265d019f9d19bfd4f45031.png" width="100%"/>
<img src="https://s3.amazonaws.com/moonup/production/uploads/1667904587646-63265d019f9d19bfd4f45031.png" width="100%"/>

[Click here](https://prompthero.com/midjourney-prompts?version=4) for more Midjourney v4 prompts and inspiration.

### 🧨 Diffusers

This model can be used just like any other Stable Diffusion model. For more information,
please have a look at the [Stable Diffusion](https://huggingface.co/docs/diffusers/api/pipelines/stable_diffusion).

You can also export the model to [ONNX](https://huggingface.co/docs/diffusers/optimization/onnx), [MPS](https://huggingface.co/docs/diffusers/optimization/mps) and/or [FLAX/JAX]().

```python
from diffusers import StableDiffusionPipeline
import torch
model_id = "nitrosocke/mo-di-diffusion"
pipe = StableDiffusionPipeline.from_pretrained(model_id, torch_dtype=torch.float16)
pipe = pipe.to("cuda")
prompt = "a magical princess with golden hair, modern disney style"
image = pipe(prompt).images[0]
image.save("./magical_princess.png")
```
