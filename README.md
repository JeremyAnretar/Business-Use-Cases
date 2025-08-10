# Greedy Portfolio Optimization (Toy Project)

This repository contains a **simple greedy algorithm** to build a toy “portfolio” using the **Wholesale customers** dataset (Kaggle).  
It’s an educational demo: we treat each spending category (Fresh, Milk, Grocery, etc.) as an “asset” and allocate a budget across them with a greedy heuristic.

> ⚠️ This is a didactic exercise to illustrate greedy optimization.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/<your-user>/<your-repo>/blob/main/<notebook>.ipynb)

---

## 📦 What’s inside
- `<notebook>.ipynb` — main notebook implementing the greedy optimizer
- `data/` — place the dataset here (ignored by git)
- `requirements.txt` — minimal dependencies
- `README.md` — this file

## 🧠 Idea in 5 lines
- Each spending category is an **asset**.
- We rescale features (0–1) so allocations are comparable.
- Objective (toy): **maximize** expected “return” minus a **risk penalty**  
  `score = w · μ  −  λ · (wᵀ Σ w)`  
  where `w` are weights (sum to 1), `μ` are per-asset scores (from data), `Σ` is a covariance proxy, and `λ` is a tunable risk-aversion.
- **Greedy step**: iteratively allocate a small budget chunk to the asset with the best *marginal* improvement of the objective, until budget is exhausted.
- It’s fast, simple, and a great baseline to compare against more advanced methods.

## 🚀 Quickstart (local)
```bash
git clone https://github.com/<your-user>/<your-repo>.git
cd <your-repo>

# (optional but recommended)
python -m venv .venv
# macOS/Linux
source .venv/bin/activate
# Windows PowerShell
# .venv\Scripts\Activate.ps1

pip install -r requirements.txt

