# TEAM5_AI2
# 🤝 ML Collaborative Project — Git & GitHub Workflow
## Team of 6 | 4 Sub-branches off `main`

---

## 📁 Repository Structure

```
ml-collaborative-project/
│
├── main/                          ← Production-ready, merged code
│   └── README.md                  ← This file
│
├── branch1_data-exploration/
│   └── data_exploration.py        ← Load & explore dataset
│
├── branch2_data-preprocessing/
│   └── data_preprocessing.py      ← Clean, encode, scale, split
│
├── branch3_model-training/
│   └── model_training.py          ← Train Linear Regression
│
└── branch4_model-evaluation/
    └── model_evaluation.py        ← Metrics + improvement techniques
```

---

## 🌿 Git Branch Commands (Run in Terminal)

### ── Leader: Initial Setup ──────────────────────────────────
```bash
# 1. Create and clone repo
git clone https://github.com/your-org/ml-collaborative-project.git
cd ml-collaborative-project

# 2. Create all 4 sub-branches from main
git checkout main
git checkout -b branch1/data-exploration
git push -u origin branch1/data-exploration

git checkout main
git checkout -b branch2/data-preprocessing
git push -u origin branch2/data-preprocessing

git checkout main
git checkout -b branch3/model-training
git push -u origin branch3/model-training

git checkout main
git checkout -b branch4/model-evaluation
git push -u origin branch4/model-evaluation
```

---

### ── Team Member Workflow (each member) ─────────────────────
```bash
# Clone the repo
git clone https://github.com/your-org/ml-collaborative-project.git
cd ml-collaborative-project

# Switch to your assigned branch (example: member on branch1)
git checkout branch1/data-exploration

# Add your script
cp /path/to/data_exploration.py .

# Stage, commit, push
git add data_exploration.py
git commit -m "feat: add EDA script with distribution plots and correlation heatmap"
git push origin branch1/data-exploration
```

---

### ── Pull Request (GitHub UI) ───────────────────────────────
```
1. Go to GitHub → Pull Requests → New Pull Request
2. base: main  ←  compare: branch1/data-exploration
3. Add title:  "feat: data exploration & EDA visualisations"
4. Add description of changes
5. Request review from team leader
6. Leader reviews → Approves → Merges
7. Repeat for all 4 branches
```

---

### ── Handling Merge Conflicts ───────────────────────────────
```bash
# If your branch is behind main
git checkout branch2/data-preprocessing
git fetch origin
git merge origin/main           # or: git rebase origin/main

# Resolve conflicts in your editor, then:
git add .
git commit -m "fix: resolve merge conflict with main"
git push origin branch2/data-preprocessing
```

---

## 👥 Team Assignment

| Branch | Script | Assigned To | Role |
|--------|--------|-------------|------|
| `branch1/data-exploration`    | `data_exploration.py`   | Member 1 & 2 | Data Analysts |
| `branch2/data-preprocessing`  | `data_preprocessing.py` | Member 3     | ML Engineer   |
| `branch3/model-training`      | `model_training.py`     | Member 4     | ML Engineer   |
| `branch4/model-evaluation`    | `model_evaluation.py`   | Member 5     | Evaluator     |
| `main` (merge + review)       | All scripts             | Leader       | Team Lead     |

---

## 📦 Dependencies

```bash
pip install pandas numpy matplotlib seaborn scikit-learn joblib
```

---

## 🔁 Data Flow Between Branches

```
Branch 1                Branch 2                 Branch 3                Branch 4
─────────────           ─────────────────        ──────────────────       ─────────────────────
data_exploration.py  →  data_preprocessing.py →  model_training.py    →  model_evaluation.py
Outputs:                Outputs:                  Outputs:                Outputs:
  raw_dataset.csv         X_train.csv               linear_regression       model_comparison
  *.png plots             X_test.csv                _model.pkl              _results.csv
                          y_train.csv               y_pred_test.csv         evaluation_*.png
                          y_test.csv                *.png plots
```

---

## ✅ Commit Message Convention

```
feat:  new feature or script
fix:   bug fix
docs:  README or comments update
data:  dataset changes
eval:  evaluation results update
```

Example:
```bash
git commit -m "feat: add StandardScaler and train-test split to preprocessing"
```
