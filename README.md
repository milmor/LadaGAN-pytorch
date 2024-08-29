## LadaGAN; Official PyTorch implementation

This repo is the official implementation of "[Efficient generative adversarial networks using linear additive-attention Transformers](https://arxiv.org/abs/2401.09596)".

<img src="./images/plot_ffhq.png" width="850px"></img>

By Emilio Morales-Juarez and Gibran Fuentes-Pineda.


## Abstract
> Although the capacity of deep generative models for image generation, such as Diffusion Models (DMs) and Generative Adversarial Networks (GANs), has dramatically improved in recent years, much of their success can be attributed to computationally expensive architectures. This has limited their adoption and use to research laboratories and companies with large resources, while significantly raising the carbon footprint for training, fine-tuning, and inference. In this work, we present LadaGAN, an efficient generative adversarial network that is built upon a novel Transformer block named Ladaformer. The main component of this block is a linear additive-attention mechanism that computes a single attention vector per head instead of the quadratic dot-product attention. We employ Ladaformer in both the generator and discriminator, which reduces the computational complexity and overcomes the training instabilities often associated with Transformer GANs. LadaGAN consistently outperforms existing convolutional and Transformer GANs on benchmark datasets at different resolutions while being significantly more efficient. Moreover, LadaGAN shows competitive performance compared to state-of-the-art multi-step generative models (e.g. DMs) using orders of magnitude less computational resources. 


## FLOPs
Using a single 12GB GPU (RTX 3080 Ti) for training on CIFAR-10 and CelebA datasets takes less than 40 hours:
| Model (CIFAR 10 32x32) | ADM-IP (80 steps) | StyleGAN2 |  VITGAN  | LadaGAN  |
| :-- |  :------:  |  :------:  |  :------:   |  :------:  |
| GPUs | Tesla V100 x 2| - |- | __RTX 3080 Ti x 1__ |
|   #Images | 69M |- |- | __68M__ |
| #Params | 57M | - |- | __19M__ |
| FLOPs | 9.0B | - | - | __0.7B__ |
| FID | __2.93__| 5.79 |4.57 | 3.29 |

| Model (CelebA 64x64)  | ADM-IP (80 steps) | StyleGAN2 |  VITGAN  | LadaGAN  |
| :-- |  :------:  |  :------:  |  :------:   |  :------:  |
| GPUs | Tesla V100 x 16| - |- | __RTX 3080 Ti x 1__ |
|   #Images | 138M |- |- | __72M__ |
| #Params | 295M | 24M | 38M | __19M__ |
| FLOPs | 103.5B | 7.8B |2.6B | __0.7B__ |
| FID | 2.67| -|3.74 | __1.81__ |

| Model (FFHQ 128x128)  | ADM-IP (80 steps) | StyleGAN2 |  VITGAN  | LadaGAN  |
| :-- |  :------:  |  :------:  |  :------:   |  :------:  |
|   #Images  | 61M | - |  - | __24M__ |
| #Params | 543M | - | - | __24M__ |
| FLOPs | 391.0B| 11.5B |11.8B| __4.3B__ |
| FID| 6.89| - | -| __4.48__ |


## BibTeX
```bibtex
@article{morales2024efficient,
  title={Efficient generative adversarial networks using linear additive-attention Transformers},
  author={Morales-Juarez, Emilio and Fuentes-Pineda, Gibran},
  journal={arXiv preprint arXiv:2401.09596},
  year={2024}
}
```
