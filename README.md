# A TinyML System for Early Screening of CHD on ESP32

This repository contains the engineering implementation for our paper, *"A TinyML System for Early Screening of CHD on ESP32"*. 

Currently, we have provided the compiled executable for the signal processing pipeline, the deep learning model, and its corresponding weights. The complete demo will be released upon the official publication of the paper.

## 📁 1. Signal Processing (`SP` Folder)

The signal processing demo is located in the `SP` folder. Due to the commercial value of the proposed algorithm, we cannot release the raw source code for the signal processing pipeline. However, we provide a compiled C/C++ executable (`.exe`) file. 

**⚠️ Note:** This executable is designed for x86 architecture computers and is **strictly for academic verification only. Do not use it for commercial purposes.**

You can process the provided heart sound `.pcm` files using the `--pcm` command. Additionally, we have included several de-identified raw `.pcm` files for verification.

### Directory Structure & Usage:

* `m.exe`: A compiled executable capable of running on x86 machines. 
  * *Execution Example:* `./m.exe --pcm yin1.pcm` (This will output the segmented data in `.txt` format).
* `model.pth`: The model weights trained on our custom dataset.
* `yin1.pcm` ~ `yin3.pcm`: Raw `.pcm` data for negative (normal) samples.
* `yang1.pcm` ~ `yang3.pcm`: Raw `.pcm` data for positive (pathological) samples.

---

## 🧠 2. Deep Learning Model (`model` Folder)

The proposed CNN-GRU model is located in the `model` folder, which contains the complete Python source code. However, the highly optimized deployable version for the ESP32 microcontroller cannot be provided due to commercial confidentiality. 

You can use our pre-segmented data to verify the model's performance on your local machine.

### Directory Structure & Usage:

* `model.ipynb`: A Jupyter Notebook used to load `.npy` data for visualization and load the model weights for inference.
* `model.pth`: The model weights trained on our dataset.
* `yin1.npy` ~ `yin3.npy`: Negative (normal) data arrays, pre-segmented using our proposed signal processing algorithm.
* `yang1.npy` ~ `yang3.npy`: Positive (pathological) data arrays, pre-segmented using our proposed signal processing algorithm.

---

## 📩 Contact & Commercial Inquiries

If you have further requirements regarding the dataset or the deployment models, please contact our commercial partner: 
**Suzhou Ruogu Xinsheng Technology Co., Ltd.**
