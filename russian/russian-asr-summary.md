# Russian ASR Evaluation

## Summary

Whisper Small produced a generally intelligible transcription of the prepared Russian speech sample, but it made errors involving compound professional terms, word order, inflection, conjunctions, and specialized audio vocabulary.

The trimmed recording achieved an approximate normalized word error rate of 12.2%. The original untrimmed runs produced higher error rates and hallucinated subtitle-credit text during trailing silence.

The most consequential error occurred when `звукоинженера и звукооператора` was transcribed as `звука инженера или звука оператора`, introducing segmentation, lexical, and semantic errors. Human review was necessary even though most of the recording’s overall meaning was preserved.

## Key Errors

| Reference                                    | Whisper Output                               | Error Type                                                       |
| -------------------------------------------- | -------------------------------------------- | ---------------------------------------------------------------- |
| `владеет и техническими аспектами профессии` | `и владеет техническими аспектами профессий` | Word order and inflection                                        |
| `звукоинженера и звукооператора`             | `звука инженера или звука оператора`         | Segmentation, lexical substitution, and conjunction substitution |
| `микширование`                               | `миксирование`                               | Technical-term substitution                                      |

## Error Patterns

### Word Order and Inflection

Whisper changed:

`владеет и техническими аспектами профессии`

to:

`и владеет техническими аспектами профессий`

The sentence remained understandable, but the conjunction was moved and `профессии` was changed to `профессий`.

### Compound-Word Segmentation

The most significant error involved:

`звукоинженера и звукооператора`

Whisper produced:

`звука инженера или звука оператора`

The model incorrectly split both compound professional terms and changed the conjunction `и` to `или`, altering the meaning of the sentence.

### Technical Vocabulary

Whisper transcribed:

`микширование`

as:

`миксирование`

The output remained understandable in context, but it did not match the spoken reference term.

### Orthographic Normalization

Whisper used `е` instead of `ё` in words such as:

* `звукорежиссер`
* `режиссер`
* `монтажер`

The reference used:

* `звукорежиссёр`
* `режиссёр`
* `монтажёр`

Because Russian commonly permits `е` in place of `ё`, these differences were treated as orthographic normalization rather than significant ASR errors.

## Hallucination Finding

The untrimmed recording caused Whisper to generate nonexistent subtitle-credit text during trailing silence. Separate runs produced different editor and proofreader names, confirming that these phrases were hallucinations rather than speech present in the recording.

Trimming the audio shortly after the final spoken sentence removed the hallucinated ending. This demonstrates the importance of checking ASR timestamps against the actual recording duration and manually reviewing silent regions.

## Severity Assessment

The Russian transcription required moderate correction:

* **Minor:** punctuation and `е` versus `ё`
* **Moderate:** word-order changes, inflection errors, and technical-term substitution
* **Major:** compound-word segmentation and a conjunction substitution that altered meaning
* **Hallucination:** fabricated subtitle-credit text during trailing silence

Most of the transcript remained readable, but several errors affected grammatical and factual precision.

## Comparison with English and Kazakh

Whisper Small performed better on Russian than on Kazakh, but worse than on English.

The English transcription preserved nearly all wording and required only light correction. The Kazakh transcription contained frequent lexical, morphological, orthographic, segmentation, and named-entity errors.

The Russian result fell between the two: most sentences remained intelligible, but compound terms, grammatical endings, and specialized vocabulary still required human review.

## Human Review

Human review was used to:

* Correct compound professional terms
* Restore the intended conjunction
* Correct word order and inflection
* Restore the reference audio terminology
* Remove hallucinated subtitle credits
* Verify the transcript against the source recording

The human-reviewed reference transcript remained the authoritative version.

## Conclusion

Whisper Small produced a usable first-pass Russian transcript, but it was not reliable enough for publication without review.

The model preserved the overall meaning, but it made important errors involving compound nouns, morphology, conjunctions, and technical vocabulary. It also hallucinated text during trailing silence until the audio was trimmed.

Compared with English and Kazakh, Russian showed intermediate ASR performance: substantially stronger than Kazakh, but less accurate than English.

## Included Files

* `russian-raw.wav`
* `russian-processed.wav`
* `russian-transcript-comparison.md`
* `russian-whisper-output.json`
* `russian-sample-metadata.md`
