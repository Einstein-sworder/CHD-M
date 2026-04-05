# A TinyML System for Early Screening of CHD on ESP32

This repository contains the engineering implementation for our paper, *"A TinyML System for Early Screening of Congenital Heart Disease (CHD) on ESP32"*.

We provide the compiled signal processing executable, trained deep learning model weights, raw heart sound PCM test files, and a complete end-to-end inference pipeline. The full deployment demo and source code will be officially released upon paper publication.

---

## 📁 Project Directory Structure
```
github/
└── model/                     # Main inference working directory
    ├── model_cnn_gru/         # Signal processing module + model weights
    │   ├── m.exe              # Compiled signal processing executable (x86)
    │   ├── model.pth          # Pre-trained CNN-GRU model weights
    │   └── output/            # Auto-generated temporary segment folder
    ├── model.ipynb            # Full end-to-end inference pipeline
    └── *.pcm                  # Raw heart sound test files
```

---

## 🧠 End-to-End Inference Pipeline (`model.ipynb`)
This notebook implements a fully automated pipeline for heart sound signal processing, segmentation, and abnormality classification.

### Features
- Automatically runs `m.exe` for PCM signal segmentation
- Loads pre-trained CNN-GRU model for inference
- Outputs heart rate, segment count, abnormal ratio, and diagnosis
- Automatically cleans temporary files after execution
- Uses **100% relative paths** for GitHub compatibility
- All configurable parameters are placed inside the `main` function

### Usage
1. Place raw heart sound `.pcm` files in the `model/` directory
2. Open `model.ipynb`
3. Modify the target PCM file in the `main` function:
   ```python
   PCM_FILE = "yin1.pcm"
   ```
4. Run the entire notebook directly

### Output Information
- Detected heart rate (BPM)
- Total heart sound segments
- Normal/abnormal prediction results
- Abnormal segment percentage
- Final diagnosis (Normal / Possible Cardiac Abnormality)

---

## 📦 Signal Processing Executable (`model_cnn_gru/m.exe`)
The signal processing pipeline is provided as a compiled executable for x86 architecture computers.

### Functions
- Resample heart sound signals to 1000 Hz
- Detect heartbeats and estimate heart rate
- Automatically segment heart sound cycles
- Export segmented data as TXT files

### Manual Execution (Optional)
```bash
cd model/model_cnn_gru
./m.exe --pcm ../yin1.pcm
```

Segmented files are saved to `model/model_cnn_gru/output/`.

**⚠️ Important Notice**
This executable is **strictly for academic verification and non-commercial use only**.

---

## 🧪 Test Dataset
De-identified raw heart sound PCM files are provided for validation:
- `yin1.pcm ~ yin3.pcm`: Normal (negative) samples
- `yang1.pcm ~ yang3.pcm`: Pathological (positive) samples

Place these files in the `model/` directory to run inference.

---

## 📩 Contact & Commercial Inquiries
For inquiries about datasets, commercial licensing, or embedded deployment, please contact our commercial partner:

**Suzhou Ruogu Xinsheng Technology Co., Ltd.**
