# Multilingual Audio, Speech Annotation, and AI Evaluation Portfolio

This repository demonstrates practical skills relevant to multilingual AI audio work, including:

- Kazakh, Russian, and English voice recording
- Verbatim and normalized transcription
- Code-switching analysis
- Audio editing and restoration
- Audio-quality evaluation
- Annotation methodology
- Automatic speech recognition evaluation
- Human review of AI-generated transcripts

## Portfolio Focus

This portfolio is designed to show the intersection of:

1. Multilingual linguistic judgment
2. Audio production and critical listening
3. Data annotation and quality assurance
4. AI model evaluation
5. Clear technical documentation

## Featured Work

### 1. Audio Editing Case Study

Location: `audio/editing-case-study/`

Includes:

- Untreated source
- Edited result
- Processing notes
- Before/after comparison
- Technical rationale and trade-offs

### 2. Kazakh Speech Annotation

Location: `annotations/kazakh/`

Includes:

- Raw and processed voice sample
- Verbatim transcript
- Normalized transcript
- English translation
- Code-switching and prosody notes
- Quality and confidence assessment

### 3. Russian Speech Annotation

Location: `annotations/russian/`

Uses the same annotation framework as the Kazakh case study for consistency.

### 4. Audio-Quality Evaluation

Location: `evaluation/audio-quality/`

Includes a scoring rubric and accept/edit/reject/escalate decisions.

### 5. ASR Evaluation

Location: `evaluation/asr/`

Compares automatic transcripts against manually reviewed references and documents:

- Substitutions
- Deletions
- Insertions
- Code-switching errors
- Proper-noun errors
- Noise-related failures
- Optional word error rate

## Methodology

The full methodology is documented in:

`docs/ANNOTATION_GUIDELINES.md`

## Repository Structure

```text
multilingual-audio-ai-portfolio/
├── README.md
├── LICENSE
├── docs/
│   ├── ANNOTATION_GUIDELINES.md
│   ├── PORTFOLIO_OVERVIEW.md
│   └── DECISION_LOG.md
├── audio/
│   ├── voice-samples/
│   │   ├── kazakh/
│   │   ├── russian/
│   │   └── english/
│   └── editing-case-study/
│       ├── before/
│       ├── after/
│       └── case-study.md
├── annotations/
│   ├── kazakh/
│   │   ├── annotations.csv
│   │   └── case-study.md
│   └── russian/
│       ├── annotations.csv
│       └── case-study.md
├── evaluation/
│   ├── audio-quality/
│   │   ├── rubric.csv
│   │   └── findings.md
│   └── asr/
│       ├── reference-transcripts.csv
│       ├── model-results.csv
│       ├── error-analysis.csv
│       └── findings.md
├── scripts/
│   ├── transcribe.py
│   ├── evaluate_asr.py
│   └── requirements.txt
└── portfolio/
    ├── master-portfolio.pdf
    ├── kazakh-role-portfolio.pdf
    ├── russian-role-portfolio.pdf
    └── audio-editing-role-portfolio.pdf
```

## Tools

Add only the tools actually used. Examples:

- FL Studio
- Focusrite audio interface
- Python
- Jupyter
- Whisper or another multilingual ASR model
- Audacity or another waveform editor

## Data and Consent

All audio in this repository should be:

- Recorded by the repository owner
- Used with explicit speaker permission
- Public-domain or properly licensed

Private conversations and copyrighted audio should not be uploaded.

## Disclosure

Automatic tools may be used for first-pass transcription, segmentation, or analysis. All final reference transcripts, linguistic judgments, and portfolio conclusions should be manually reviewed.

## Contact

Add your preferred professional contact information here.
