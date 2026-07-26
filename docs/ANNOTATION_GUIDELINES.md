# Transcript Annotation Guidelines

## Purpose

These guidelines define how human-reviewed reference transcripts and Whisper outputs are compared in this portfolio.

The goal is to apply the same review process across Kazakh, Russian, and English.

## Reference Transcript

The reference transcript represents the words actually spoken in the recording.

For prepared readings, the original script may be used as the reference only after confirming that the speaker did not omit, repeat, or change any words while recording.

The audio recording remains the final source of truth.

## Verbatim Transcription

The verbatim transcript should preserve:

* Spoken words
* Repetitions
* False starts
* Fillers
* Code-switching
* Incomplete phrases
* Noticeable spoken errors

Do not silently correct grammar in a verbatim transcript.

## Normalized Transcription

A normalized transcript may:

* Add punctuation
* Correct capitalization
* Remove accidental fillers
* Standardize spelling
* Correct obvious grammatical errors

Normalization must not change the intended meaning.

## Error Categories

### Substitution

Whisper replaces a spoken word with a different word.

Example:

```text
Reference: микширование
Whisper: миксирование
```

### Deletion

Whisper omits a spoken word, syllable, or grammatical ending.

Example:

```text
Reference: аламын
Whisper: алам
```

### Insertion

Whisper adds a word or phrase that was not spoken.

Example:

```text
Reference: audio effects, mixing
Whisper: audio effects, as well as mixing
```

### Segmentation Error

Whisper incorrectly joins or separates words.

Example:

```text
Reference: звукоинженера
Whisper: звука инженера
```

### Word-Order Error

Whisper recognizes words but places them in the wrong order.

### Morphological Error

Whisper changes a grammatical ending, case, tense, number, or suffix.

### Named-Entity Error

Whisper incorrectly transcribes a person, place, organization, school, or other proper noun.

### Orthographic Difference

The wording is recognized correctly, but the spelling differs.

Examples include:

* `е` instead of `ё` in Russian
* British versus American English spelling
* Capitalization differences

Orthographic differences should be documented but may be excluded from normalized error calculations.

### Punctuation Error

Whisper changes sentence boundaries, commas, dashes, or capitalization without changing the spoken meaning.

### Hallucination

Whisper generates words that are not supported by the recording.

Hallucinations may occur during:

* Silence
* Background noise
* Very quiet speech
* Repeated decoding
* The end of a recording

## Severity Levels

### Minor

The meaning remains fully clear.

Examples:

* Punctuation differences
* Capitalization
* Regional spelling
* `е` versus `ё`

### Moderate

The sentence remains understandable, but correction is needed.

Examples:

* Grammatical endings
* Small lexical substitutions
* Article changes
* Word-order errors

### Major

The error changes factual information, meaning, or intelligibility.

Examples:

* Incorrect place names
* Incorrect professional terms
* Severe phrase distortion
* Conjunction substitutions that change meaning

### Hallucination

The model creates content that was not spoken.

Hallucinations should always be removed from the final transcript.

## Confidence

Use the following confidence labels when manually reviewing a segment:

* High: wording is clearly audible
* Medium: wording is mostly clear but one part is uncertain
* Low: audio is unclear or multiple interpretations are possible

## Human Review Process

1. Listen to the recording.
2. Compare the recording with the original script.
3. Create or verify the reference transcript.
4. Compare Whisper output with the reference.
5. Record meaningful differences.
6. Classify each difference by error type.
7. Assign severity.
8. Remove unsupported hallucinated text.
9. Document any normalization decisions.

## Language-Specific Notes

### Kazakh

Pay particular attention to:

* Grammatical suffixes
* Vowel harmony
* Place names
* Institutional names
* Regional pronunciation
* Russian or English code-switching

### Russian

Pay particular attention to:

* Compound professional terms
* Grammatical case endings
* `е` and `ё`
* Conjunction changes
* Technical terminology

### English

Pay particular attention to:

* Sentence boundaries
* Article substitutions
* Hyphenation
* British and American spelling
* Inserted linking phrases

## Final Rule

The human-reviewed transcript is the authoritative version.

Whisper output should be treated as a draft that requires validation before publication or downstream use.
