# Simplified DRAW Model for Image Generation (Fashion-MNIST)
This project implements a simplified version of the **DRAW (Deep Recurrent Attentive Writer)** model for image generation using the Fashion-MNIST dataset.

The goal is to study how recurrent generative models can iteratively refine image reconstructions and learn meaningful latent representations under limited computational resources.

## Objectives

- Implement a simplified DRAW-style recurrent generative model
- Train the model on a lightweight dataset (Fashion-MNIST)
- Analyze the impact of:
  - Latent dimension
  - KL regularization (β)
- Evaluate reconstruction and generation quality

## Model Overview

The architecture is inspired by the DRAW paper and includes:

- Encoder LSTM
- Latent variable sampling (reparameterization trick)
- Decoder LSTM
- Iterative canvas refinement

Unlike the original DRAW model, this implementation does not include the attention-based read/write mechanism for simplicity.

## Experiments

We conducted the following experiments:

### 1. Latent Dimension Study
- Compared latent dimensions: 8, 16, 32
- Evaluated reconstruction quality and latent representation capacity

### 2. KL Regularization (β-VAE)
- Tested β values: 0.5, 1.0, 2.0
- Observed trade-off between:
  - Reconstruction accuracy
  - Latent space regularization

 ## Results

- The model successfully reconstructs Fashion-MNIST images
- Generates coherent samples from random latent vectors
- Larger latent dimensions improve reconstruction quality
- Higher β values enforce stronger regularization but reduce reconstruction accuracy

## Sample Outputs

### Reconstructions
![reconstructions](images/recon.png)

### Generated Samples
![generated](images/generated.png)

## Limitations

- Simplified DRAW model (no attention mechanism)
- Limited to small grayscale dataset
- Performance can be improved with deeper architectures and longer training

## Conclusion

This project demonstrates that a simplified DRAW-style recurrent generative model can effectively learn meaningful representations and generate realistic images on a small dataset.

Future work could include:
- Attention-based read/write mechanism
- Application to more complex datasets
- Improved latent space regularization techniques

## Tech Stack

- Python
- PyTorch
- NumPy
- Matplotlib

## Project Structure
draw-fashion-mnist-generative-model/
│
├── notebook.ipynb
├── README.md
├── images/
│   ├── recon.png
│   ├── generated.png
└── requirements.txt

## Installation

```bash
git clone https://github.com/your-username/draw-fashion-mnist-generative-model.git
cd draw-fashion-mnist-generative-model
pip install -r requirements.txt
```

---

## Run

```markdown
Open the notebook:
jupyter notebook notebook.ipynb
```
---

# Add Images

```python
plt.savefig("images/recon.png")
plt.savefig("images/generated.png")
```
