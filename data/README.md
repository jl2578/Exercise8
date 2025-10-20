# Data Directory

This directory contains the essential data files for the NAcc reward processing analysis.

## Included Files (committed to repository):
- `nacc_bilateral_mask.nii` - NAcc ROI mask (required for analysis)
- `qc_nacc_roi_alignment.png` - Quality control visualization

## Auto-Downloaded Files:
When you run the notebook, it will automatically download subject data from OpenNeuro:
- `sub-s001/`, `sub-s002/`, `sub-s003/`, `sub-s004/` - Subject folders
- Each contains BOLD fMRI and events files (~300MB per subject)

**Note:** Downloaded files are cached locally, so subsequent runs are fast. The auto-download system ensures you always have the latest data without bloating the repository.

## Expected Structure After First Run:
```
data/
├── nacc_bilateral_mask.nii         ← Committed
├── qc_nacc_roi_alignment.png       ← Committed  
├── sub-s001/                       ← Auto-downloaded
│   └── func/
│       ├── sub-s001_task-mid_run-01_bold.nii.gz
│       └── sub-s001_task-mid_run-01_events.tsv
├── sub-s002/ ... sub-s004/         ← Downloaded as needed
```