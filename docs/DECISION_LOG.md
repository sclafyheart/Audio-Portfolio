# Decision Log

## ASR Model

**Decision:** Use Whisper Small as the shared baseline for Kazakh, Russian, and English.

**Reason:** Whisper Small ran reliably on the available hardware and allowed the same model to be compared across all three languages.

A Medium model was attempted for Kazakh but did not complete reliably, so it was not used as the primary evaluation model.

## Audio Format

**Decision:** Convert ASR input files to mono, 16 kHz, 16-bit PCM WAV.

**Reason:** This format is widely compatible with speech-recognition systems and provides a consistent input format across different languages.

## Reference Transcripts

**Decision:** Use human-reviewed transcripts as the ground truth.

**Reason:** Whisper output contained substitutions, segmentation errors, grammatical errors, and hallucinations. The audio recording remained the final source of truth.

## Russian Trailing Silence

**Decision:** Trim the Russian recording after the final spoken sentence.

**Reason:** The untrimmed recording caused Whisper to generate nonexistent subtitle-credit text during trailing silence.

The untrimmed result was retained as an example of model hallucination, while the trimmed result was used as the main Russian ASR output.

## Orthographic Normalization

**Decision:** Treat minor spelling conventions separately from meaningful recognition errors.

Examples include:

* Russian `е` versus `ё`
* English `theatre` versus `theater`
* Capitalization and punctuation

These differences were documented but were not treated as major semantic errors.

## Kazakh Evaluation

**Decision:** Keep the Whisper Small Kazakh output even though it contained many errors.

**Reason:** The poor result is an important finding. It demonstrates the need for native-speaker review and highlights differences in model performance across languages.

## Published Outputs

**Decision:** Publish one primary Whisper JSON output per language.

**Reason:** Multiple experimental JSON files would make the repository harder to understand. Secondary runs are only retained when they demonstrate a meaningful failure mode, such as the Russian trailing-silence hallucination.
