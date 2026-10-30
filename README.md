# Text Summarizer using T5 (HuggingFace Transformers)

A dialogue summarization app. I fine-tuned `t5-small` on the SAMSum dataset and built a web app on top of it using FastAPI.

## Features
- Fine-tuned T5-small model for summarizing chat conversations
- FastAPI backend with a simple web page (paste text, click Summarize)

## Training Details
- Model: `t5-small`
- Dataset: SAMSum (4000 train samples, 500 validation samples)
- Epochs: 6
- Batch size: 8
- Weight decay: 0.01, warmup steps: 500
- Final result: Training Loss 0.415, Validation Loss 0.374

## Project Files
- `Text_summarizer.ipynb`: training and testing notebook
- `app.py`: FastAPI backend
- `index.html`: web page
- `requirements.txt`: dependencies

## How to Run
1. Clone the repo and install dependencies:
   ```
   pip install -r requirements.txt
   ```
2. Place the trained model folder `saved_summary_model` in the project folder (it is not included in this repo because of its size).
3. Start the app:
   ```
   python -m uvicorn app:app --reload
   ```
4. Open `http://127.0.0.1:8000` in your browser.

## Example
Input:
```
Amit: Hey, are we meeting tomorrow?
Riya: Yes, at 5 pm near the cafe.
Amit: Okay, I will bring the notes.
Riya: Great, see you then!
```
Output:
```
Amit is meeting at 5 pm near the cafe. He will bring the notes.
```

## Tech Stack
Python, PyTorch, HuggingFace Transformers, FastAPI, Uvicorn, Jinja2