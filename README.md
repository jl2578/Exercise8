# Exercise 8: NAcc Reward Processing Analysis

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)](https://github.com/codespaces/new?hide_repo_select=true&ref=main)

An interactive neuroimaging analysis exploring reward anticipation in the nucleus accumbens (NAcc) using real fMRI data from the Monetary Incentive Delay (MID) task.

## 🚀 Quick Start in GitHub Codespaces

1. **Click the Codespaces badge above** or open this repository in Codespaces
2. Wait for the environment to build (~2-3 minutes)
3. Open `Exercise8.ipynb`
4. **Choose your subject** by changing `SUBJECT = "sub-s001"` to any of:
   - `"sub-s001"`, `"sub-s002"`, `"sub-s003"`, or `"sub-s004"`
5. **Run all cells** - data downloads automatically on first run

## 📊 What You'll Analyze

- **Real fMRI data** from the Adolescent Health and Development in Context (AHDC) study
- **Nucleus accumbens responses** to reward vs neutral cues during anticipation
- **Event-locked timecourses** showing when the brain "lights up" for rewards
- **Statistical comparisons** with bootstrap confidence intervals and effect sizes

## 🧠 Learning Objectives

By completing this exercise, you will:

1. **Extract time-series** from brain regions using fMRI masks
2. **Build trial-type arrays** separating reward vs neutral conditions  
3. **Generate publication-quality plots** showing reward anticipation dynamics
4. **Compute effect sizes** and confidence intervals for neuroscience data
5. **Connect artificial neural networks** (from BuildingABrain.ipynb) to real brain circuits

## 📁 Repository Structure

```
exercise-8-nacc-analysis/
├── Exercise8.ipynb              ← Main analysis notebook
├── requirements.txt             ← Python dependencies
├── .devcontainer/              ← Codespaces configuration
│   └── devcontainer.json
├── data/                       ← Data folder
│   ├── README.md              ← Data documentation
│   ├── nacc_bilateral_mask.nii ← NAcc ROI mask (included)
│   ├── qc_nacc_roi_alignment.png ← QC image (included)
│   └── sub-s00X/              ← Subject data (auto-downloaded)
├── figs/                      ← Generated plots
└── README.md                  ← This file
```

## 🔬 Data Source & Citation

This exercise uses **real fMRI data** from the Adolescent Health and Development in Context (AHDC) study:

> Baldwin M. Way, Christopher R. Browning, Dylan D. Wagner, Jodi L. Ford, Bethany Boettner & Ping Bai (2025).  
> _Structural and functional MRI dataset from the Adolescent Health and Development in Context (AHDC) study in Columbus, Ohio._  
> OpenNeuro [Dataset] doi:10.18112/openneuro.ds005901.v1.0.0

## 🛠 Technical Details

- **Auto-download system**: Subject data (~300MB per subject) downloads automatically from OpenNeuro
- **Caching**: Downloaded files persist in your Codespace for fast re-runs
- **No manual setup**: All dependencies install automatically via `requirements.txt`
- **Cross-platform**: Works in any environment that supports Jupyter notebooks

## 🎯 Key Results

The analysis reveals that:
- NAcc shows **higher activation for reward vs neutral cues** during anticipation
- Peak responses occur **~5-7 seconds post-cue** due to hemodynamic lag
- Effect sizes are **small-to-medium** (Cohen's d ≈ 0.3-0.6) at the individual level
- This provides neural evidence for **incentive salience** - the brain learning to "want" reward-predicting cues

## 🤝 For Instructors

- Students can work independently with any of the 4 available subjects
- All dependencies are pre-configured for Codespaces
- Generated figures save to `figs/` for easy inclusion in reports
- QC checks ensure data integrity before analysis begins

## 📋 Requirements

- GitHub account (for Codespaces)
- Basic Python/Jupyter familiarity
- No local software installation needed

---

**Ready to explore how your brain responds to rewards? Click the Codespaces badge and start analyzing! 🧠💰**