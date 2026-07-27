# Multilingual Audio and ASR Portfolio

## Overview

This portfolio demonstrates multilingual speech recording, audio processing, automatic speech recognition evaluation, transcript review, and error analysis in Kazakh, Russian, and English.

The project compares Whisper Small outputs against human-reviewed reference transcripts. It focuses on identifying linguistic errors, hallucinations, language-specific weaknesses, and the level of human review required before ASR output can be used reliably.

## Languages

* Kazakh
* Russian
* English

## Tools

* OpenAI Whisper Small
* Python
* FFmpeg
* FL Studio
* Shure SM58 microphone
* Focusrite Scarlett 2i2 audio interface

## Recording Workflow

Each sample was recorded in WAV format and exported in two versions:

* Raw recording
* Lightly processed recording

ASR-ready copies were converted to:

* Mono
* 16 kHz sample rate
* 16-bit PCM WAV

The raw or ASR-ready recording was transcribed with Whisper Small.

## Evaluation Workflow

For each language:

1. Record a speech sample.
2. Create a human-reviewed reference transcript.
3. Run the recording through Whisper Small.
4. Compare the Whisper transcript with the reference.
5. Identify lexical, grammatical, segmentation, spelling, and hallucination errors.
6. Categorize the severity of the errors.
7. Summarize the findings in a language-specific evaluation report.

## Main Findings

### English

Whisper Small produced a highly accurate transcript. Most differences involved punctuation, article choice, regional spelling, or minor phrase formatting.

### Russian

Whisper Small produced a generally intelligible transcript but made errors involving compound professional terms, word order, inflection, conjunctions, and specialized audio vocabulary.

The untrimmed recording also caused Whisper to hallucinate subtitle-credit text during trailing silence.

### Kazakh

Whisper Small preserved the broad subject of the recording but produced frequent lexical, morphological, orthographic, segmentation, and named-entity errors.

The Kazakh transcript required substantially more native-speaker correction than the Russian and English transcripts.

Each language folder contains:

* Raw recording
* Processed recording
* Human-reviewed reference transcript
* Whisper JSON output
* Transcript comparison
* ASR evaluation summary
* Recording metadata

## Purpose

This project demonstrates the ability to:

* Evaluate multilingual speech-recognition output
* Review transcripts for linguistic accuracy
* Identify ASR hallucinations
* Categorize language-specific errors
* Work with multilingual audio data
* Communicate technical findings clearly
* Apply native-speaker judgment to Kazakh and Russian speech
