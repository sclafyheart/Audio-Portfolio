# Russian ASR Evaluation

## Summary

Whisper Small produced a generally intelligible transcription of the prepared Russian speech sample, but it made errors involving compound professional terms, word order, inflection, conjunctions, and specialized audio vocabulary.

The trimmed recording achieved an approximate normalized word error rate of 12.2%. The original untrimmed runs produced higher error rates and hallucinated subtitle-credit text during trailing silence.

The most consequential error occurred when `звукоинженера и звукооператора` was transcribed as `звука инженера или звука оператора`, introducing both segmentation and semantic errors. Human review was necessary even though the overall meaning of most of the recording was preserved.

## Key Errors

| Reference | Whisper Output | Error Type |
|---|---|---|
| `владеет и техническими аспектами профессии` | `и владеет техническими аспектами профессий` | Word order and inflection |
| `звукоинженера и звукооператора` | `звука инженера или звука оператора` | Segmentation and conjunction substitution |
| `микширование` | `миксирование` | Technical-term substitution |
| `с помощью` | `с с помощью` | Repeated-word insertion |

## Hallucination Finding

The untrimmed recording caused Whisper to generate nonexistent subtitle-credit text during trailing silence. Trimming the file after the final spoken sentence removed the hallucinated ending.

## Included Files

- `russian-raw.wav`
- `russian-processed.wav`
- `russian-reference-transcript.md`
- `russian-whisper-output.json`
- `russian-sample-metadata.md`
