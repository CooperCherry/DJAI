# DJAI — local starter

## Move from Colab to VS Code

1. Extract this ZIP into your desired project folder. Open the **folder** in VS Code.
2. Install Python 3.11 or 3.12 and the VS Code Python and Jupyter extensions.
3. In the VS Code terminal, create and activate a virtual environment:

   **macOS/Linux:** `python3 -m venv .venv` then `source .venv/bin/activate`

   **Windows PowerShell:** `py -m venv .venv` then `.\.venv\Scripts\Activate.ps1`

4. Run `python -m pip install -r requirements.txt`.
5. Copy your audio files into `data/audio/` (never commit copyrighted audio).
6. Open `notebooks/DJAI_stage1.ipynb`, choose the `.venv` kernel, and run cells in order.
7. To create a **new** GitHub repository, run:

   `git init`
   `git add .`
   `git commit -m "Initialize cleaned DJAI stage 1"`
   `git branch -M main`
   `git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git`
   `git push -u origin main`

   Create the empty repository on GitHub first. If you already have a repository, clone it and copy these files in instead; do not run `git init` in a separate history.

## Files

- `notebooks/DJAI_stage1.ipynb`: clean pipeline + existing scoring functions + candidate generator.
- `data/audio/`: local audio inputs, ignored by Git.
- `data/processed/`: generated candidate CSV, ignored by Git.
- `requirements.txt`: Python dependencies.

## Important source limitation

The provided notebook ends at a heading for real-audio testing. It does **not** contain the audio rendering implementation mentioned in the conversation. This starter does not claim to render transitions. Keep a backup of the original notebook and migrate any separately stored renderer in a later step.

## Migration notes

Removed: Google Drive mounting, Colab-only paths and pip magics, repeated waveform/envelope exports, exploratory plots, unverified downbeat identification, intermediate CSV exports, and manually assembled track-pair tables. Retained: key estimation and original rhythm/harmonic/energy/phrase scoring functions. Replaced: ingestion and segment construction with a minimal local-path pipeline.
