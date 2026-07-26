# English ASR Evaluation

## Summary

Whisper Small produced a highly accurate transcription of the prepared English speech sample. The model preserved nearly all of the original wording, sentence order, technical terminology, and meaning.

Most differences were minor and involved punctuation, article choice, phrase insertion, and word formatting rather than major recognition failures. Unlike the Kazakh sample, the English output did not contain severe lexical substitutions, distorted named entities, or widespread morphological errors.

The transcription was generally usable with light human review.

## Key Errors

| Reference                                       | Whisper Output                                   | Error Type                                 |
| ----------------------------------------------- | ------------------------------------------------ | ------------------------------------------ |
| `recording—the placing of microphones`          | `recording, the placing of microphones`          | Punctuation normalization                  |
| `levels. The physical recording`                | `levels, the physical recording`                 | Sentence-boundary error                    |
| `set up, sound check, and do live sound mixing` | `set up soundcheck and do live sound mixing`     | Punctuation and word-formatting difference |
| `a sound reinforcement system`                  | `the sound reinforcement system`                 | Article substitution                       |
| `theatre`                                       | `theater`                                        | Regional spelling normalization            |

## Error Patterns

### Sentence-Boundary Error

Whisper failed to separate two sentences in the first paragraph.

Reference:

```text
the setting of levels. The physical recording of any project is done by an engineer.
```

Whisper:

```text
the setting of levels, the physical recording of any project is done by an engineer.
```

This is mainly a punctuation and segmentation issue rather than a speech-recognition failure.

### Word Formatting

The phrase:

```text
sound check
```

was transcribed as:

```text
soundcheck
```

Both forms are understandable, but the reference used two words.

Similarly, Whisper removed commas around the phrase and changed:

```text
set up, sound check, and do
```

to:

```text
set up soundcheck and do
```

### Article Substitution

Reference:

```text
a sound reinforcement system
```

Whisper:

```text
the sound reinforcement system
```

This is a minor grammatical substitution. The overall meaning remains unchanged.

### Regional Spelling

Reference:

```text
theatre
```

Whisper:

```text
theater
```

This reflects British versus American spelling rather than a meaningful recognition error. For normalized WER calculations, these forms may be treated as equivalent if spelling normalization is documented.

## Severity Assessment

The English transcription required only light correction.

The errors can be grouped as:

* **Minor:** punctuation, commas, capitalization, and regional spelling
* **Moderate:** small insertions, article substitutions, and sentence-boundary errors
* **Major:** none observed

The content remained clear and accurate throughout the recording.

## Comparison with Russian and Kazakh

Whisper Small performed best on the English recording.

The Russian sample was mostly intelligible but contained errors involving compound words, inflection, technical vocabulary, and trailing-silence hallucination.

The Kazakh sample contained frequent lexical, morphological, orthographic, segmentation, and named-entity errors that required extensive native-speaker correction.

The English sample, by comparison, preserved nearly all content and required only minor editing.

This demonstrates a substantial performance difference across languages despite using the same model family and a similar recording setup.

## Human Review

Human review corrected:

* One inserted phrase
* One sentence-boundary error
* Minor punctuation differences
* One article substitution
* Word formatting for `sound check`
* Regional spelling normalization

The Whisper output was sufficiently accurate to serve as a strong draft transcript, but the reference transcript remains the authoritative version.

## Conclusion

Whisper Small produced a strong English transcription with only minor grammatical, punctuation, formatting, and spelling differences.

The result was largely suitable for direct use after light human review. Compared with the Russian and Kazakh recordings, the English sample showed substantially higher recognition accuracy and fewer meaning-altering errors.

## Included Files

* `english-raw.wav`
* `english-processed.wav`
* `english-sample-metadata.md`
* `english-whisper-output.json`
* `english-transcript-comparison.md`
