# Wan2GP on Kaggle

A Kaggle notebook that runs [Wan2GP](https://github.com/deepbeepmeep/Wan2GP) and redirects all model downloads to `/kaggle/tmp` instead of the 20GB working directory.

## Files

- `wan2gp_kaggle.ipynb` — the notebook. Run the cells in order, top to bottom.

## What the notebook does

1. **Download Wan2GP** — clones the repo into `/kaggle/working`, or pulls the latest changes if it already exists.
2. **Install requirements** — `pip install -r requirements.txt`.
3. **Set model download path to `/kaggle/tmp`** — symlinks the `ckpts` folder to `/kaggle/tmp/ckpts` and points the Hugging Face cache at `/kaggle/tmp/hf`. Run this **before** launching the app.
4. **Launch Wan2GP** — runs `python wgp.py --share --profile 5` and prints a public Gradio link.

## Usage

1. Open `wan2gp_kaggle.ipynb` in Kaggle (import it as a notebook).
2. Enable a GPU accelerator and Internet in the notebook settings.
3. Run all cells in order.
4. Open the Gradio link that appears in the last cell.

## Notes

- Models download to `/kaggle/tmp` the first time you use them, keeping the working directory small.
- `/kaggle/tmp` is temporary disk space and is cleared when the session ends, so model downloads will repeat on a fresh session.
