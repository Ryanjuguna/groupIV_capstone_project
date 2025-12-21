# Breast Cancer Prediction — Group IV

Short capstone project to build a lightweight, interpretable machine learning model to help prioritize breast cancer diagnostics.

## Project Overview
- Purpose: Provide a clinician-friendly risk prediction tool using routine clinical features.
- Key ideas: interpretability, low computational cost, clear performance tracking and a simple web demo.

## Team
- Vincent Nyakach — Project Lead
- Esther Mutiria — Web Developer
- Ryan Muchaba — Data Scientist
- Vyone Vulimu — Researcher
- Brian Mutiso — Data Analyst

(Replace with final member names/roles if needed.)

## What’s in this repo
- `index.htm` — Project landing page and demo UI
- `style.css` — Styles for the UI

## Run locally
- Recommended: install VS Code Live Server extension and click **Go Live** for `index.htm`.
- Without Live Server (Windows PowerShell):

```powershell
Start-Process '.\groupIV_capstone_project\index.htm'
```

## Notes & Next Steps
- Replace placeholder values (stats, member photos, detailed model results) as you obtain validated results.
- Add the training and model code in a new `model/` or `notebooks/` directory when ready.
 - Add a site background image (e.g., your wrinkled pink paper) to `assets/pink-paper.jpg`.
	 - Recommended: JPEG or WebP, ~1920×1200 for full-screen, optimized for web (compress to < 300KB if possible).
	 - If `assets/pink-paper.jpg` is missing the site will automatically fall back to the soft pink gradients.
 - (Optional) Add `assets/desc-bg.jpg` to apply a background image specifically to the Project Description card. The card uses a 30% translucent white overlay by default; tweak `--desc-overlay-opacity` in `style.css` to change the opacity.

## License
Add a license file if you plan to open-source this project.
