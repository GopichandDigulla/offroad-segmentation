🌍 Offroad Terrain Segmentation

This project focuses on semantic segmentation of offroad environments using deep learning.
We performed three training experiments to progressively improve performance.

---

🚀 Objective

Segment offroad terrain into 10 classes such as:

-background
- Trees 🌳
- Lush Bushes 🌿
- Dry Grass 🌾
- Dry Bushes
- Ground Clutter
- Logs
- Rocks 🪨
- Landscape
- Sky ☁️

---

🧪 Training Experiments

---

🔹 Run 1 — Baseline Model

Configuration:

- Batch Size: 2
- Learning Rate: 1e-4
- Epochs: 10
- Optimizer: SGD
- Loss: CrossEntropy
- Augmentation: ❌

Result:

- Basic segmentation learned
- Low IoU
- Slow convergence

## Train 1 – Baseline

| Metric | Train | Validation |
|--------|-------|-----------|
| Loss | - | - |
| IoU | 0.50 | 0.48 |
| Dice | - | - |
| Accuracy | - | - |

---

🔹 Run 2 — Improved Setup

Configuration:

- Batch Size: 4
- Learning Rate: 5e-5
- Epochs: 25
- Optimizer: AdamW
- Loss: CrossEntropy

Changes:

- SGD ➝ AdamW
- More epochs
- Bigger batch

Result:

- Better stability
- Improved IoU



## Train 2 – Improved

| Metric | Train | Validation |
|--------|-------|-----------|
| Loss | - | - |
| IoU | 0.57 | 0.56 |
| Dice | - | - |
| Accuracy | - | - |

---
🔹 Run 3 — SegFormer-B3 (Final)

Configuration:

- Model: SegFormer-B3
- Batch Size: 4
- Learning Rate: 5e-5
- Epochs: 10
- Optimizer: AdamW

Loss:

- CrossEntropy + Dice Loss


## Train 3 – SegFormer

| Metric | Train | Validation |
|--------|-------|-----------|
| Loss | 0.3452 | 0.4107 |
| IoU | 0.6280 | 0.5895 |
| Dice | 0.7582 | 0.7639 |
| Accuracy | 0.8725 | 0.8729 |

---
📊 Final Results

-Metric           | Value
-Train Loss       | 0.3452
-Val Loss         | 0.4107
-Train IoU        | 0.6280
-Val IoU          | 0.5895
-Train Dice       | 0.7582
-Val Dice         | 0.7639
-Train Accuracy   | 0.8725
-Val Accuracy     | 0.8729

---

🏆 Best Results

- Best Val IoU: 0.5899 (Epoch 8)
- Best Val Dice: 0.7640
- Best Val Accuracy: 0.8735
- Lowest Val Loss: 0.4105


## Best Results

| Metric | Value | Epoch |
|--------|-------|-------|
| Best Val IoU | 0.5899 | 8 |
| Best Val Dice | 0.7640 | 8 |
| Best Val Accuracy | 0.8735 | 8 |
| Lowest Val Loss | 0.4105 | 9 |
---

📈 Key Insights

- Increasing epochs alone ≠ big improvement
- AdamW > SGD for stability
- Biggest improvement came from:

👉 SegFormer (Transformer model)

- Dice Loss improves segmentation quality

---



⚙️ Installation

pip install torch torchvision transformers opencv-python matplotlib tqdm



📦 Dataset
## 📦 Dataset

The dataset used in this project is provided by the organizers.

Offroad_Segmentation_Training_Dataset/
Important links
 
Create a falcon account: https://falcon.duality.ai/auth/sign-up?utm_source=hackathon&utm_medium=instructions&utm_campaign=Hawkathon

Download Dataset: https://falcon.duality.ai/secure/documentation/hackathon-segmentation-desert?utm_source=hackathon&utm_medium=instructions&utm_campaign=Hawkathon

After downloading, extract and place it in:

---
📁 Project Structure

scripts/
 ├── train_segmentation.py
 ├── test_segmentation.py
 ├── visualize.py

segformer_train_stats/
predictions/
models/
README.md

---
model download link
https://drive.google.com/file/d/1omSO54sMdrkcdOWPceplZbr4oOqFXNFQ/view?usp=sharing


---

▶️ Run

python train_segmentation.py

---

🔧 Future Work

- Improve IoU → 0.8+
- Data augmentation
- Class balancing
- Better tuning

---

👨‍💻 Author

Gopichand
AI & ML Developer
