# Multilingual Audio and ASR Evaluation Portfolio

This repository demonstrates practical skills in multilingual speech recording, audio processing, automatic speech recognition evaluation, transcript review, and audio editing.

The portfolio includes original voice recordings and human-reviewed ASR analyses in:

* Kazakh
* Russian
* English

It also includes an audio-editing case study focused on vocal cleanup, processing, and mixing decisions.

## Portfolio Focus

This portfolio demonstrates the intersection of:

1. Multilingual linguistic judgment
2. Audio production and critical listening
3. ASR transcript evaluation
4. Human review of AI-generated output
5. Error classification and quality assurance
6. Clear technical documentation

## Featured Work

### 1. Kazakh ASR Evaluation

Location:

```text
kazakh/
```

Includes:

* Raw Kazakh recording
* Lightly processed recording
* Human-reviewed reference transcript
* Whisper Small JSON output
* Original-versus-Whisper transcript comparison
* Detailed ASR evaluation summary

The Kazakh analysis focuses on:

* Lexical substitutions
* Morphological errors
* Orthographic errors
* Word segmentation
* Named-entity recognition
* Regional pronunciation
* Native-speaker review

Whisper preserved the broad topic of the recording but produced frequent errors that required substantial correction.

### 2. Russian ASR Evaluation

Location:

```text
russian/
```

Includes:

* Raw Russian recording
* Lightly processed recording
* Human-reviewed reference transcript
* Whisper Small JSON output
* Original-versus-Whisper transcript comparison
* Detailed ASR evaluation summary

The Russian analysis focuses on:

* Compound-word segmentation
* Inflection
* Word order
* Conjunction substitution
* Specialized audio terminology
* Trailing-silence hallucination

The untrimmed Russian recording caused Whisper to generate nonexistent subtitle-credit text. Trimming the trailing silence removed the hallucinated ending.

### 3. English ASR Evaluation

Location:

```text
english/
```

Includes:

* Raw English recording
* Lightly processed recording
* Human-reviewed reference transcript
* Whisper Small JSON output
* Original-versus-Whisper transcript comparison
* Detailed ASR evaluation summary

The English transcript was highly accurate and required only minor correction involving:

* Punctuation
* Sentence boundaries
* Article choice
* Phrase insertion
* Word formatting
* British and American spelling differences

### 4. Audio Editing Case Study

Location:

```text
audio-editing/
```

Includes:

* Before audio
* After audio
* Editing and mixing case study
* Optional processing-chain screenshots

The case study documents:

* Initial audio-quality assessment
* Cleanup and clip-gain decisions
* Equalization
* Compression
* De-essing
* Reverb or delay
* Automation
* Trade-offs between clarity, dynamics, and naturalness

## Cross-Language Findings

Using Whisper Small with a similar recording setup produced noticeably different results across the three languages.

### English

Whisper produced a highly accurate transcript with mostly minor punctuation and formatting differences.

### Russian

Whisper produced a generally intelligible transcript but made several important errors involving compound terms, morphology, conjunctions, and technical vocabulary.

### Kazakh

Whisper preserved the general topic but produced frequent lexical, morphological, orthographic, segmentation, and named-entity errors.

The results demonstrate the importance of human review, especially for multilingual and lower-resource speech-recognition tasks.

## Methodology

The annotation and evaluation process is documented in:

```text
docs/ANNOTATION_GUIDELINES.md
```

The general workflow was:

1. Record an original voice sample.
2. Export raw and lightly processed versions.
3. Convert an ASR-ready copy to mono, 16 kHz, 16-bit PCM WAV.
4. Transcribe the recording using Whisper Small.
5. Compare the ASR result with a human-reviewed reference transcript.
6. Identify meaningful errors.
7. Classify errors by type and severity.
8. Document language-specific findings.
9. Remove unsupported hallucinated content.
10. Treat the audio recording as the final source of truth.

## Error Categories

The evaluations use the following categories:

* Substitution
* Deletion
* Insertion
* Word-order error
* Segmentation error
* Morphological error
* Named-entity error
* Orthographic difference
* Punctuation error
* Hallucination

Error severity is classified as:

* Minor
* Moderate
* Major
* Hallucination

## Repository Structure

```text
multilingual-audio-ai-portfolio/
├── README.md
├── LICENSE
│
├── docs/
│   ├── ANNOTATION_GUIDELINES.md
│   ├── PORTFOLIO_OVERVIEW.md
│   └── DECISION_LOG.md
│
├── kazakh/
│   ├── kazakh-raw.wav
│   ├── kazakh-processed.wav
│   ├── kazakh-whisper-output.json
│   ├── kazakh-transcript-comparison.md
│   └── kazakh-asr-summary.md
│
├── russian/
│   ├── russian-raw.wav
│   ├── russian-processed.wav
│   ├── russian-whisper-output.json
│   ├── russian-transcript-comparison.md
│   └── russian-asr-summary.md
│
├── english/
│   ├── english-raw.wav
│   ├── english-processed.wav
│   ├── english-whisper-output.json
│   ├── english-transcript-comparison.md
│   └── english-asr-summary.md
│
└── audio-editing/
    ├── vocal-mix-before.wav
    ├── vocal-mix-after.wav
    ├── editing-case-study.md
    └── images/
        ├── vocal-processing-chain.png
        └── corrective-eq.png
```

The `images/` folder is optional and should contain only screenshots that clearly support the editing case study.

## Tools and Equipment

* OpenAI Whisper Small
* Python
* FFmpeg
* FL Studio
* Shure SM58 microphone
* Focusrite Scarlett 2i2 audio interface

## Human Review

Whisper output was treated as a first-pass transcript rather than ground truth.

All final reference transcripts and conclusions were manually reviewed for:

* Spoken-word accuracy
* Grammar and morphology
* Proper nouns
* Technical terminology
* Word boundaries
* Meaning-changing substitutions
* Unsupported hallucinations

The audio recording remained the authoritative source.

## Data and Consent

All speech recordings in this repository were created by the repository owner.

No private conversations or third-party copyrighted speech recordings are included.

Audio-editing examples should contain only:

* Original recordings
* Original music
* Properly licensed material
* Material used with explicit permission

## Disclosure

AI-assisted tools may have been used for organization, formatting, and first-pass analysis.

All final linguistic judgments, reference transcripts, error classifications, and conclusions were manually reviewed.

## Contact

* Name: Azat Kossanov
* Email: kossanov.azat@gmail.com
* LinkedIn: linkedin.com/in/azat-kossanov
