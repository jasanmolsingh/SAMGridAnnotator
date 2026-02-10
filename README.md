[![DOI](https://zenodo.org/badge/1154590897.svg)](https://doi.org/10.5281/zenodo.18600184)
[![License](https://img.shields.io/badge/license-MIT-blue.svg)](LICENSE)


# 🌿 SAMGridAnnotations

**Interactive Image Annotation using Meta's Segment Anything Model (SAM)**

---

## 🧠 What is this?

This repository helps you create **segmentation masks** for images using Meta AI’s powerful **Segment Anything Model (SAM)**.

👉 In simple words:

Instead of manually drawing shapes around plants, soil, weeds, etc…

1️⃣ The program scans the image.

<img width="1920" height="1080" alt="0GridCreation_GridPointActivation" src="https://github.com/user-attachments/assets/e1e71121-0f63-4663-a6ca-77a3680ecc49" />

2️⃣ The AI suggests masks

<img width="1920" height="1080" alt="1MaskSelection" src="https://github.com/user-attachments/assets/2e81e166-db7a-4d31-bbf3-ad63fe797895" />

3️⃣ You click the best one and choose a class

<img width="1920" height="1080" alt="2ClassSelection" src="https://github.com/user-attachments/assets/0006a00e-38e2-4a76-a333-dba83f0b9024" />

4️⃣ Selected mask is saved. Continue!

<img width="1920" height="1080" alt="3Selectedmask_Saved" src="https://github.com/user-attachments/assets/bc42e3b8-27c4-4bc0-8349-08f6114b6ffb" />


5️⃣ Done! Final mask of the image saves after all gridpoints are complete. 


This makes dataset creation MUCH faster.

---
## ☘️ Current Usage

✳️ This code is generated specifically for forage mixtures with **Alfalfa, Tall fescue, White clover, Weed, Backgound and Soil** as classes. For other objects, please change the classes and labels in the code.

---

## 🎯 What does this tool do?

For every image:

1️⃣ Places a smart grid of points on the image 

2️⃣ AI generates **3 mask options** 

3️⃣ You select the best mask 

4️⃣ Choose the correct label (Weed, Soil, etc.) 

5️⃣ Mask is automatically saved 

💡 You can stop anytime — the tool resumes from where you left off!

---

## ⚙️ Requirements (VERY IMPORTANT)

Install:

* Python **3.9 or 3.10 recommended**
* GPU is optional but strongly recommended (makes SAM MUCH faster)

---

## 📥 Step 1 — Clone this Repository

```bash
git clone https://github.com/jasanmolsingh/SAMGridAnnotations.git
cd SAMGridAnnotations
```
---

## 📦 Step 2 — Install Dependencies

Create a virtual environment (recommended):

### ✅ Windows

```bash
python -m venv SAMGridAnnotations
SAMGridAnnotations\Scripts\activate
```

### ✅ Mac/Linux

```bash
python3 -m venv SAMGridAnnotations
source SAMGridAnnotations/bin/activate
```

Now install packages:

```bash
pip install -r requirements.txt
```

---

## 🧠 Step 3 — Download SAM Model (REQUIRED)

⚠️ The tool **WILL NOT work** without this.

Download the checkpoint:

👉 [https://github.com/facebookresearch/segment-anything](https://github.com/facebookresearch/segment-anything)

Download:

```
sam_vit_b.pth
```

✍️ Rename the downloaded file to "sam_vit_b.pth", if original filename is different.


Create a folder:

```
weights/
```

Put the file inside:

```
weights/sam_vit_b.pth
```



---

## 📁 Step 4 — Folder Structure

Your project should look like this:

```
SAMGridAnnotations/
│
├── SAMGridAnnotations.ipynb
├── requirements.txt
├── README.md
│
├── weights/
│     sam_vit_b.pth
│
└── dataset_mixture/
      ├── images/
      │     └── train/
      │           your_images_here.jpg
      │
      └── masks/
            └── train/
                  (auto-created)
```

👉 Just drop your images inside:

```
dataset_mixture/images/train/
```

---

## ▶️ Step 5 — Run the Notebook

Start Jupyter:

```bash
jupyter notebook
```

Open:

```
SAMGridAnnotations.ipynb
```

Click:

```
Run → Run All Cells
```

---

## 🖱️ How Annotation Works (SUPER SIMPLE)

### ✅ Blue dots appear

These are the points SAM will test.

### ✅ One dot turns RED

This is the active point.

### ✅ AI shows 3 masks

Pick the best one — or skip.

### ✅ Choose a class

A popup lets you select:

* Weed
* Soil
* Alfalfa
* White Clover
* Tall Fescue
* Background

DONE ✅

---

## 💾 What Gets Saved?

For every annotation you accept:

### ✔️ Grayscale Mask

Pixel numbers represent classes.

Example:

```
image1_class2_mask.png
```

---

### ✔️ Colored Mask with Legend

Helps you visually confirm labels.

```
image1_rgb_legend.png
```

---

## 🔁 Can I Stop and Resume?

YES 👍

The tool tracks progress automatically.

If it crashes or you stop:

👉 Restart it — it continues where you left off.

No work is lost.

---

## 🚨 Common Problems

### ❌ SAM not loading?

Check that:

```
weights/sam_vit_b.pth
```

exists.

---

### ❌ Windows popup not showing?

Run locally — not on remote servers.

Tkinter needs a GUI.

---

### ❌ CUDA not detected?

Install the GPU version of PyTorch:

👉 [https://pytorch.org/](https://pytorch.org/)

---

## ⭐ Pro Tips (Highly Recommended)

✔ Use a GPU
✔ Start with 5–10 images to test
✔ Keep backups of masks
✔ Do NOT rename output files

---

## 🙌 Credits

* Meta AI — Segment Anything Model
* OpenCV
* PyTorch
---

## 🙌 Acknowledgement

The research work and data collection for this project was conducted in the KAMS Lab (Dept. of Agricultural Sciences, Clemson University). 

KAMS Lab (https://bulent931.wixsite.com/bulent/kams-lab)

---

## 🔬 Reproducibility

This repository is archived with Zenodo and assigned a DOI to ensure long-term reproducibility of the software.

To reproduce results:

1. Clone the repository
2. Install dependencies from `requirements.txt`
3. Download SAM weights
4. Run the notebook

For version-specific reproduction, use the archived release linked via DOI.

---

## 👤 Author
Jasanmol Singh, M.Sc.

Ph.D. Student | Clemson University, Clemson, SC, USA

[Email](jasanms@clemson.edu) | [Personal Website](https://sites.google.com/view/jasanmolsingh/about)

---

## 💬 Questions?

Open a GitHub issue and I’ll help!
