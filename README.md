# Image Super-Resolution using an Improved Generative Adversarial Network

This project implements a perceptual single-image super-resolution (SISR) system based on an improved SRGAN architecture. The model integrates Residual-in-Residual Dense Blocks (RRDBs), perceptual loss, and a relativistic adversarial objective to enhance texture realism while maintaining reconstruction fidelity.

The project was completed as part of a graduate-level course and received an **A+** grade.

---

## 🔍 Key Features
- ESRGAN-style RRDB generator (no batch normalization)
- PatchGAN discriminator with relativistic average least-squares GAN (RaLSGAN)
- Perceptual loss using VGG-19 feature representations
- Mixed-precision (AMP) training for efficiency
- ×4 super-resolution on natural images

---

## 📊 Results

### Training Dynamics
![PSNR vs Epoch](experiments/psnr_vs_epoch.png)

### Qualitative Results
Low-resolution input → Super-resolved output → Ground truth

![Qualitative Results](experiments/qualitative_results_1.png)

The proposed model produces sharper edges and more coherent textures than bicubic upsampling and a baseline SRGAN, while maintaining competitive PSNR/SSIM values.

---

## 📁 Dataset
- **Unsplash Image Super-Resolution Dataset (Kaggle)**
- LR–HR pairs generated via bicubic downsampling (×4)

See `datasets/README.md` for setup instructions.

---

## 🚀 Usage

### Training
```bash
python train.py --config configs/train.yaml
