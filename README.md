# Deep Learning Coursework

**Author:** Kseniia Tikhonova  
**Environment:** Google Colab | TensorFlow 2.19.0 | Python 3.12 | T4 GPU

Comparative study of deep learning architectures across four domains:
synthetic data, computer vision, sequential modelling, and generative models.
All experiments are tracked in `experiment_log.csv` (auto-generated on run).

---

## Contents

| Section | Topic | Dataset | Best result |
|---------|-------|---------|-------------|
| 3 | Fully connected networks | Synthetic 2D (disk vs annulus) | FC-16-8: test acc **1.00** |
| 4–5 | CNN | MNIST | val acc **0.9928** |
| 6 | Transfer learning | Cat/Dog (Kaggle, 128×128) | VGG16+ImageNet: val acc ~**0.9563** |
| 7 | LSTM | ECG heartbeats, 5 classes (MIT-BIH + PTBDB) | val acc ~**0.8286** |
| 8 | DCGAN | MNIST | — |
| 9 | Convolutional Autoencoder | MNIST / FashionMNIST | — |
| 10 | Super-resolution GAN | Cat/Dog | — |
| 11 | Unit tests | — | 7/7 passed |

---

## How to run

1. Open `dl_course_homeworks_tikhonova.ipynb` in Google Colab
2. Set runtime to **GPU (T4)**
3. Run all cells in order — seeds and the experiment logger are initialised in Section 1–2
4. The Kaggle dataset download (Section 6) requires a Kaggle API key:
    enter your username and key when needed.

No `requirements.txt` needed; the notebook uses the standard Colab environment plus:

```
pip install opendatasets
```

---

## Reproducibility

- Global seed: `SEED = 42` (Python, NumPy, TensorFlow, PYTHONHASHSEED)
- `TF_DETERMINISTIC_OPS=1` to reduce GPU nondeterminism
- Remaining nondeterminism: cuDNN backward-pass variance in Conv2D on GPU

---

## Experiment tracking

Every run is appended to `experiment_log.csv` (created automatically):

```
timestamp, experiment, epochs, val_accuracy
..., FC-16-8, 20, 1.0
..., CNN-MNIST, 10, 0.9928
..., VGG16-transfer, 10, 0.9563
..., LSTM-ECG, 10, 0.8286
```

---

## License

Code: original coursework, free for educational use.  
Datasets: Kaggle ToU (Cat/Dog), CC0-1.0 (SR Cat/Dog), public domain (MNIST), MIT (FashionMNIST).
