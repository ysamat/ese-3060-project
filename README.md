# ESE 3060 — Final Project  
Speedrunning Training Efficiency for CIFAR-10 + NanoGPT

This repository contains our work for the ESE 3060 Final Project, which focuses on improving training efficiency in two domains:

### 🟢 Part 1 — CIFAR-10 Speedrun  
Goal: Improve training time for a VGG-style image classification model.  
We will experiment with data augmentation, initialization, optimizer selection, network structure changes, and more.

### 🔵 Part 2 — NanoGPT Speedrun  
Goal: Modify and optimize a GPT-style language model training loop to reduce compute and convergence time.  
We will propose algorithmic and system-level improvements, test them with ablations, and benchmark results.

---

## 📂 Repository Structure

ese-3060-project/  
├── cifar10/                      # PART 1 — CIFAR-10 training experiments  
│   ├── baseline/                  # Original unmodified runs & logs  
│   └── experiments/               # Each idea/sub-experiment lives here  
│                                   # Ex: experiments/skip_connection/  
│                                   #     experiments/augmentations/  
│                                   #     experiments/new_optimizer/  
│  
├── nanogpt/                      # PART 2 — NanoGPT language model speedrun  
│   ├── baseline/                  # Raw baseline performance logs  
│   └── experiments/               # Sub-experiments for LLM improvements  
│                                   # Ex: experiments/squared_relu/  
│                                   #     experiments/flash_attention/  
│  
└── reports/                      # Final written deliverables  
    ├── figures/                   # Plots, timing graphs, loss curves  
    ├── part1.pdf                  # One-page CIFAR-10 write-up  
    └── part2.pdf                  # Two-page NanoGPT engineering report  

---

## 🛠 How to Run Locally

Clone the repo:

    git clone https://github.com/<username>/ese-3060-project.git
    cd ese-3060-project

Install dependencies:

    pip install -r requirements.txt

---

## 🚀 Running Experiment Code

CIFAR-10 (Part 1):

    cd cifar10
    python airbench94.py

NanoGPT (Part 2):

    cd nanogpt
    python cached_fineweb10B.py 9
    torchrun --standalone --nproc_per_node=8 train_gpt.py

---

## 🔬 Experiment Workflow

1. Create a new folder inside `cifar10/experiments/` or `nanogpt/experiments/`.
2. Copy the base script into your experiment directory.
3. Modify the code to test a hypothesis.
4. Log runtime, training loss, GPU usage, and accuracy.
5. Compare results against baselines.
6. Include figures and tables in `reports/figures/` for the write-up.

---

## 👥 Collaboration (GitHub Workflow)

Each modification should be done on a separate branch:

    git checkout -b experiment-name

When complete:

    git add .
    git commit -m "Added experiment: <name>"
    git push origin experiment-name

Then open a Pull Request on GitHub to merge into `main`.

---

## 📌 Deliverables

| Part | Files | Description |
| --- | --- | --- |
| Part 1 | Code, 1-page report, logs | CIFAR-10 training optimization |
| Part 2 | Code, 2-page report, logs | NanoGPT training optimization |

Extra credit is available for measurable speed improvements on the provided evaluation setup.
