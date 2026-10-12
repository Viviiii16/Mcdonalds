# 🎙️ Meeting Assistant

An end-to-end pipeline that turns raw meeting audio into a clean, readable, final transcript. It detects speech, transcribes it, refines the text, and produces a polished document, all through three Colab-friendly Jupyter notebooks.

---

## 📑 Table of Contents
- [Overview](#-overview)
- [Features](#-features)
- [How It Works](#-how-it-works)
- [Repository Structure](#-repository-structure)
- [Getting Started](#-getting-started)
- [Usage](#-usage)
- [Example](#-example)
- [Configuration](#-configuration)
- [Tech Stack](#-tech-stack)
- [Limitations](#-limitations)
- [Roadmap](#-roadmap)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

---

## 🔍 Overview

Meeting recordings are long, noisy, and hard to search. Raw speech-to-text output is often full of filler words, false starts, misheard terms, and missing punctuation.

**Meeting Assistant** solves this with a three-stage pipeline:

1. **Detect and transcribe** speech from audio to produce a raw transcript.
2. **Refine** the raw transcript to fix errors and improve readability.
3. **Generate** a final, well-formatted transcript document.

---

## ✨ Features

- 🎧 Speech detection and transcription from meeting audio
- 🧹 Transcript refinement (cleanup, correction, formatting) `TODO: list specifics`
- 📄 Final document generation `TODO: output format`
- 📓 Fully notebook-based, with no local setup needed on Google Colab
- 🔁 Run each stage independently or the whole pipeline at once
- `TODO: speaker labels / timestamps / summaries / action items, if supported`

---

## ⚙️ How It Works

```
┌──────────────┐    ┌───────────────────────┐    ┌──────────────────┐    ┌──────────────────┐
│ Meeting audio│ →  │ Stage 1: STT          │ →  │ Stage 2: Refine  │ →  │ Stage 3: Document│
│              │    │ Detect + transcribe   │    │ Clean up text    │    │ Final transcript │
└──────────────┘    └───────────────────────┘    └──────────────────┘    └──────────────────┘
                          Raw transcript          Refined transcript       Final transcript
```

### Stage 1: Speech Detection and Transcription
**Notebook:** `final_stt_(1).ipynb`

The final speech detection model. It detects speech segments in the audio, transcribes them, and outputs a **raw transcript**.

- **Model / library:** `TODO`
- **Input:** audio file `TODO: formats`
- **Output:** raw transcript `TODO: format`

### Stage 2: Transcript Refinement
**Notebook:** `stage2_refine_colab_3 (1).ipynb`

Takes the raw transcript and outputs a **refined transcript**.

- **Approach:** `TODO: e.g. LLM-based, rule-based`
- **What it fixes:** `TODO: e.g. filler words, punctuation, casing, misheard terms`
- **Input:** raw transcript from Stage 1
- **Output:** refined transcript

### Stage 3: Final Document
**Notebook:** `stage3_document_colab_2 (1).ipynb`

Takes the refined transcript and outputs the **final transcript**.

- **Processing:** `TODO`
- **Input:** refined transcript from Stage 2
- **Output:** final transcript `TODO: format`

### Full Pipeline
**Notebook:** `meeting_assistant_full.ipynb`

Runs all three stages end to end in a single notebook.

---

## 📁 Repository Structure

```
Mcdonalds/
├── final_stt_(1).ipynb                 # Stage 1: speech detection + raw transcription
├── stage2_refine_colab_3 (1).ipynb     # Stage 2: transcript refinement
├── stage3_document_colab_2 (1).ipynb   # Stage 3: final transcript generation
├── meeting_assistant_full.ipynb        # Complete pipeline (Stages 1–3)
├── .gitattributes
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- A Google account (for Google Colab), **or** a local Jupyter environment
- Python 3.x `TODO: confirm version`
- A GPU runtime is recommended for faster transcription `TODO: confirm`
- API keys, if any: `TODO`

### Installation

1. **Clone the repository**
```bash
   git clone https://github.com/Viviiii16/Mcdonalds.git
   cd Mcdonalds
```

2. **Open a notebook**
   - **Google Colab:** upload the notebook at [colab.research.google.com](https://colab.research.google.com) (File → Upload notebook), or open it directly from GitHub.
   - **Local Jupyter:**
```bash
     pip install jupyter
     jupyter notebook
```

3. **Install dependencies**
   Run the first cell of the notebook, which installs the required packages. `TODO: add requirements.txt`

---

## 🧪 Usage

### Option A: Run the full pipeline (recommended)

1. Open `meeting_assistant_full.ipynb`.
2. Set the runtime to GPU `TODO: if applicable` (Runtime → Change runtime type).
3. Upload your meeting audio or set the file path in the config cell.
4. Run all cells (Runtime → Run all).
5. Find the final transcript in `TODO: output location`.

### Option B: Run stage by stage

Use this if you want to inspect or tweak intermediate outputs.

| Step | Notebook | You provide | You get |
|------|----------|-------------|---------|
| 1 | `final_stt_(1).ipynb` | Meeting audio | Raw transcript |
| 2 | `stage2_refine_colab_3 (1).ipynb` | Raw transcript | Refined transcript |
| 3 | `stage3_document_colab_2 (1).ipynb` | Refined transcript | Final transcript |

---

## 📝 Example

**Raw transcript (Stage 1)**
```
TODO: paste a short sample of raw output
```

**Refined transcript (Stage 2)**
```
TODO: paste the same sample after refinement
```

**Final transcript (Stage 3)**
```
TODO: paste the same sample as final output
```

---

## 🔧 Configuration

| Setting | Description | Default |
|---------|-------------|---------|
| Audio path | Location of the input audio file | `TODO` |
| Model size / name | Speech model used in Stage 1 | `TODO` |
| Language | Language of the meeting | `TODO` |
| Output directory | Where results are saved | `TODO` |

---

## 🛠 Tech Stack

- **Language:** Python
- **Environment:** Jupyter Notebook / Google Colab
- **Speech-to-text:** `TODO`
- **Refinement:** `TODO`
- **Document generation:** `TODO`

---

## ⚠️ Limitations

- Transcription accuracy depends on audio quality, background noise, and accents.
- Very long recordings may need chunking or more memory. `TODO: confirm`
- `TODO: language support, speaker diarization, etc.`

---

## 🗺 Roadmap

- [ ] Add a `requirements.txt` and pin dependency versions
- [ ] Convert the notebooks into a reusable Python package or CLI
- [ ] Speaker diarization (who said what)
- [ ] Meeting summary and action-item extraction
- [ ] Export to multiple formats (PDF, DOCX, Markdown)
- [ ] Simple web UI (e.g. Gradio or Streamlit)

---

## 🩺 Troubleshooting

| Problem | Possible fix |
|---------|--------------|
| Out-of-memory error in Colab | Switch to a GPU runtime or use a smaller model |
| Poor transcription quality | Use cleaner audio or a larger model |
| Missing package errors | Re-run the install cell and restart the runtime |
| Notebook won't open from GitHub | Download the `.ipynb` and upload it to Colab manually |

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m "Add your feature"`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request
