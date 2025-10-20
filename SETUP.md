# Repository Setup Guide

## ✅ What's Included in the Repository

This repository contains **only the essential files** needed to run the analysis. Large data files are **auto-downloaded** when students run the notebook.

### Files Committed to GitHub:

```
exercise-8-nacc-analysis/
├── Exercise8.ipynb                  ← Main analysis notebook
├── requirements.txt                 ← Python dependencies
├── environment.yml                  ← Conda environment (optional)
├── README.md                       ← Student-facing documentation
├── .gitignore                      ← Excludes large files
├── .devcontainer/
│   └── devcontainer.json           ← Codespaces configuration
├── data/
│   ├── README.md                   ← Data documentation
│   ├── nacc_bilateral_mask.nii     ← NAcc ROI mask (2MB, committed)
│   ├── qc_nacc_roi_alignment.png   ← QC image (~100KB, committed)
│   ├── sub-s001/func/.gitkeep      ← Empty folder placeholder
│   ├── sub-s002/func/.gitkeep      ← Empty folder placeholder
│   ├── sub-s003/func/.gitkeep      ← Empty folder placeholder
│   └── sub-s004/func/.gitkeep      ← Empty folder placeholder
└── figs/
    └── .gitkeep                    ← Output folder placeholder
```

## 🔄 How the Auto-Download Works

1. Student opens repository in GitHub Codespaces
2. Student selects a subject by changing `SUBJECT = "sub-s001"` (or 002, 003, 004)
3. Student runs the notebook
4. The auto-download cell detects missing files and downloads them from OpenNeuro:
   - `sub-s00X_task-mid_run-01_bold.nii.gz` (~300MB, compressed)
   - `sub-s00X_task-mid_run-01_events.tsv` (~5KB)
5. Files are decompressed and cached in `data/sub-s00X/func/`
6. Subsequent runs skip downloading (uses cached files)

## 📦 Repository Size

- **Without data:** ~2.5 MB (just mask + QC image + code)
- **After download (1 subject):** ~303 MB (one subject's data)
- **Maximum (all 4 subjects):** ~1.2 GB (if student downloads all)

## 🚫 What's Excluded (.gitignore)

The `.gitignore` file prevents large data files from being committed:

```gitignore
# Auto-downloaded subject data (large BOLD files)
data/sub-*/func/*.nii
data/sub-*/func/*.nii.gz
data/sub-*/func/*.tsv

# Generated outputs
figs/*.png
figs/*.jpg
!figs/.gitkeep
```

## 🧪 Testing the Setup

### Local Testing:
```bash
# Clone the repository
git clone <your-repo-url>
cd exercise-8-nacc-analysis

# Install dependencies
pip install -r requirements.txt

# Open the notebook
jupyter notebook Exercise8.ipynb

# Select a subject and run all cells
# Data will auto-download on first run
```

### Codespaces Testing:
1. Click the "Open in Codespaces" badge in README.md
2. Wait for environment to build (~2-3 minutes)
3. Open Exercise8.ipynb
4. Run all cells - data downloads automatically

## 📝 Notes for Instructors

### Why This Structure?

1. **Small repository**: Only 2.5 MB committed, fast to clone
2. **No large file storage**: Avoids GitHub LFS or size limits
3. **Always fresh data**: Downloads from OpenNeuro ensure latest version
4. **Student choice**: Each student picks 1 of 4 subjects
5. **Cached downloads**: After first run, analysis is instant

### Required Files in Repository:

- ✅ `nacc_bilateral_mask.nii` - Essential for ROI extraction
- ✅ `qc_nacc_roi_alignment.png` - Visual QC for students
- ✅ Empty `sub-s00X/func/` folders - Download targets

### Not Included in Repository:

- ❌ BOLD fMRI files (~300MB each) - Auto-downloaded
- ❌ Events TSV files - Auto-downloaded
- ❌ Generated figures - Created by students

## 🔧 Maintenance

### Updating the Mask File:
```bash
# Replace the mask file
cp new_nacc_mask.nii data/nacc_bilateral_mask.nii
git add data/nacc_bilateral_mask.nii
git commit -m "Update NAcc mask"
git push
```

### Adding a New Subject:
```bash
# Create folder structure
mkdir -p data/sub-s005/func
echo "# This folder will contain downloaded BOLD and events files" > data/sub-s005/func/.gitkeep

# Update notebook documentation (cell 3)
# Add "sub-s005" to the available subjects list

git add data/sub-s005/
git commit -m "Add sub-s005 folder structure"
git push
```

## 🆘 Troubleshooting

**Students report "file not found" errors:**
- Check that empty `sub-s00X/func/` folders exist with .gitkeep files
- Verify auto-download cell runs without errors
- Confirm OpenNeuro dataset is accessible

**Repository size too large:**
- Check `.gitignore` is properly excluding `data/sub-*/func/*.nii*`
- Run `git ls-files --cached` to see what's tracked
- Remove accidentally committed large files with `git filter-branch`

**Codespaces build fails:**
- Verify `requirements.txt` lists correct package versions
- Check `.devcontainer/devcontainer.json` syntax is valid
- Test locally first with `pip install -r requirements.txt`

---

**This structure keeps the repository lean while providing students with a seamless, one-click analysis environment!** 🚀