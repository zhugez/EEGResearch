# EEGResearch

Dự án này nhằm mục đích phân tích và xử lý dữ liệu EEG để nghiên cứu các tín hiệu thần kinh phản ứng với các kích thích thính giác. Chúng tôi sẽ thực hiện các bước như phân tích khám phá dữ liệu (EDA), tiền xử lý tín hiệu, chuyển đổi giá trị thực, trực quan hóa dữ liệu và đánh giá hiệu suất mô hình. Mục tiêu cuối cùng là phát triển các mô hình phân loại hoặc dự đoán chính xác, giúp cải thiện các ứng dụng sinh trắc học dựa trên EEG và hiểu sâu hơn về mối quan hệ giữa tín hiệu thần kinh và các kích thích thính giác.
# EEGResearch

[![License](https://img.shields.io/github/license/zhugez/EEGResearch)](./LICENSE)
![Stars](https://img.shields.io/github/stars/zhugez/EEGResearch?style=social)
![Last Commit](https://img.shields.io/github/last-commit/zhugez/EEGResearch)

**EEGResearch** is a research project focused on **auditory EEG signals** for **biometric identification** and **signal processing in healthcare AI**.  
It serves as part of my PhD research, combining **denoising frameworks**, **feature extraction**, and **metric learning models**.

---

## 🚀 Features
- EEG signal preprocessing (filtering, normalization, artifact removal).
- Denoising strategies (ICA, Wavelet Transform, GAN-based augmentation).
- Feature extraction: spectrograms, frequency-domain features, deep embeddings.
- Biometric identification pipeline using **metric learning (ArcFace / Siamese nets)**.
- Reproducible experiment tracking with **MLflow**.

---

## 📂 Project Structure
```
EEGResearch/
├── data/              # raw + processed EEG (not uploaded, link below)
├── preprocess/        # denoising, filtering scripts
├── features/          # feature extraction methods
├── models/            # model definitions (CNN, ResNet, ArcFace, etc.)
├── experiments/       # configs + training scripts
├── results/           # output metrics, plots
└── README.md
```

---

## 📊 Dataset
We use publicly available auditory EEG datasets from **PhysioNet**:  
- [Auditory EEG dataset](https://physionet.org/content/auditory-eeg/1.0.0/)  
(Download instructions in `data/README.md`)

> ⚠️ Dataset is large, so it is not included in this repo. Please follow the instructions above to download.

---

## 🧪 How to Run

1. Create environment:
```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
```

2. Preprocess data:
```bash
python preprocess/denoise.py --input data/raw --output data/clean
```

3. Train model:
```bash
python experiments/train.py --config configs/arcface.yaml
```

4. Track experiments with MLflow:
```bash
mlflow ui
```

---

## 📈 Results (example)
| Model            | Accuracy | EER | Notes |
|------------------|----------|-----|-------|
| CNN baseline     | 82.5%    | 0.19| Raw spectrograms |
| ResNet-18        | 88.3%    | 0.14| With preprocessing |
| ArcFace ResNet34 | 91.2%    | 0.10| Metric learning + denoising |

---

## 📖 Citation
If you use this code or dataset preprocessing, please cite:
```bibtex
@misc{ly2025eegresearch,
  author       = {Ly, Ngoc Vu},
  title        = {EEGResearch: Auditory EEG for Biometric Identification},
  year         = {2025},
  publisher    = {GitHub},
  howpublished = {\url{https://github.com/zhugez/EEGResearch}},
}
```

---

## 📜 License
Distributed under the **Apache 2.0 License**. See [LICENSE](./LICENSE) for details.
