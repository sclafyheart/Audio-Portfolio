# Multilingual Speech and Audio Annotation Guidelines

**Version:** 1.0  
**Languages:** Kazakh, Russian, English  
**Purpose:** Portfolio demonstration for multilingual speech annotation, audio evaluation, and AI training-data quality work.

## 1. Scope

These guidelines define a consistent process for:

- Transcribing spoken Kazakh, Russian, and English
- Distinguishing verbatim and normalized transcripts
- Annotating code-switching, disfluencies, prosody, and non-speech events
- Documenting audio quality and uncertainty
- Producing reference transcripts for automatic speech recognition evaluation
- Making defensible accept, edit, reject, or escalate decisions

These guidelines are a portfolio methodology, not a claim of being an official industry standard.

## 2. Core Principles

1. **Transcribe what is heard, not what was probably intended.**
2. **Do not silently correct the speaker in the verbatim transcript.**
3. **Preserve intentional code-switching.**
4. **Document uncertainty instead of guessing.**
5. **Apply the same rule consistently across similar clips.**
6. **Separate linguistic accuracy from audio-quality judgments.**
7. **Keep an auditable record of important annotation decisions.**

## 3. Required Output for Each Clip

Each annotated clip should include:

- File name
- Language or language mix
- Speaker identifier
- Start and end timestamps
- Verbatim transcript
- Normalized transcript
- English translation when the source is not English
- Prosodic notes when relevant
- Non-speech labels when relevant
- Audio-quality notes
- Confidence score
- Reviewer decision
- Brief rationale for ambiguous cases

## 4. File Naming

Use lowercase file names with hyphens or underscores.

Recommended format:

`<language>_<sample-type>_<speaker>_<version>.<extension>`

Examples:

- `kazakh_conversational_spk01_raw.wav`
- `kazakh_conversational_spk01_processed.wav`
- `russian_codeswitch_spk01_raw.wav`
- `english_reading_spk01_raw.wav`

Transcript files should use the same base name:

- `kazakh_conversational_spk01_annotations.csv`
- `kazakh_conversational_spk01_notes.md`

## 5. Speaker Labels

Use neutral speaker identifiers:

- `SPEAKER_01`
- `SPEAKER_02`
- `SPEAKER_UNKNOWN`

Do not place personal names in public annotation files unless the speaker has explicitly consented.

## 6. Timestamping

Use the format:

`[HH:MM:SS.mmm–HH:MM:SS.mmm]`

For short clips, this is acceptable:

`[00:03.240–00:07.810]`

Create one segment per complete utterance or meaningful phrase. Avoid splitting a word across two segments.

## 7. Verbatim Transcription

The verbatim transcript preserves audible speech, including:

- Fillers
- Repetitions
- False starts
- Self-corrections
- Incomplete phrases
- Code-switched words
- Meaningful discourse markers

Example:

`Мен, ээ, кеше студияға бардым да, сосын... сосын вокалды қайта жаздым.`

Do not correct grammar or replace informal wording in the verbatim transcript.

## 8. Normalized Transcription

The normalized transcript improves readability while preserving meaning.

It may:

- Remove fillers
- Remove accidental repetitions
- Resolve obvious false starts
- Standardize punctuation
- Expand approved abbreviations
- Standardize number formatting according to project rules

Example:

**Verbatim:**  
`Мен, ээ, кеше студияға бардым да, сосын... сосын вокалды қайта жаздым.`

**Normalized:**  
`Мен кеше студияға бардым да, сосын вокалды қайта жаздым.`

Do not translate code-switched words in the normalized transcript unless the task explicitly requires translation.

## 9. Code-Switching

Preserve each word in the language in which it was spoken.

Record the language mix in metadata:

- `kk`
- `ru`
- `en`
- `kk-ru`
- `ru-en`
- `kk-ru-en`

Examples:

- `Сосын мен meeting-ке кешігіп қалдым.`
- `Я потом export жасап жібердім.`

Do not replace a code-switched word merely because an equivalent exists in another language.

When a foreign root takes a Kazakh or Russian ending, transcribe the spoken form as accurately as possible and explain the morphology in the annotation note when relevant.

## 10. Fillers and Disfluencies

Retain audible fillers in the verbatim transcript.

Common examples include:

- Kazakh: `ээ`, `мм`, `жаңағы`
- Russian: `э`, `эм`, `ну`, `как бы`
- English: `uh`, `um`, `like`

Use plain orthographic forms unless a project requires phonetic transcription.

### Repetitions

Retain accidental repetition in verbatim text:

`Мен мен ертең барамын.`

Normalize only in the normalized transcript:

`Мен ертең барамын.`

### False Starts

Use a dash for an abandoned word or phrase when clearly audible:

`Мен ерте- ертең барамын.`

### Long Pauses

Use `[pause]` only when the pause is meaningfully longer than normal phrasing or affects interpretation.

## 11. Non-Speech Events

Use square-bracket labels.

Approved labels:

- `[laughter]`
- `[cough]`
- `[breath]`
- `[music]`
- `[background noise]`
- `[door closes]`
- `[phone vibration]`
- `[overlapping speech]`
- `[pause]`
- `[unclear]`
- `[inaudible]`

Use a specific label when the event is identifiable. Use `[background noise]` when it is not useful to identify the source.

## 12. Unclear and Inaudible Speech

Use `[unclear]` when speech is audible but cannot be confidently identified.

Use `[inaudible]` when the speech is masked, missing, clipped, or too quiet to recover.

Before assigning either label:

1. Listen to the local segment at least twice.
2. Listen again in full-sentence context.
3. Check whether the uncertainty is caused by noise, overlap, accent, speed, or recording failure.
4. Avoid inserting a low-confidence guess into the reference transcript.

When a likely interpretation is useful, place it in the notes, not in the reference transcript.

## 13. Pronunciation and Accent

Do not mark a regional pronunciation as an error solely because it differs from a standard variety.

Separate:

- Regional or dialectal variation
- Speaker-specific accent
- Casual reduction
- Mispronunciation
- Recording artifact
- ASR error

Use neutral language in notes.

Preferred:

`Regional pronunciation; intelligible and internally consistent.`

Avoid:

`Incorrect accent.`

## 14. Prosody

Add prosodic labels only when they are relevant to the task.

Possible fields:

- Intonation: falling, rising, level
- Stress: neutral, emphatic, contrastive
- Rhythm: regular, hesitant, rushed
- Speaking rate: slow, moderate, fast
- Emotion: neutral, positive, frustrated, uncertain, excited
- Delivery: scripted, spontaneous, conversational

Do not infer emotion when the evidence is weak. Use `uncertain` when necessary.

## 15. Punctuation and Capitalization

Use standard orthographic punctuation in normalized transcripts.

In verbatim transcripts:

- Use commas and periods to support readability.
- Do not add punctuation that changes meaning.
- Use question marks when the utterance is clearly interrogative.
- Capitalize names and sentence beginnings according to the language's conventions.

## 16. Numbers, Dates, and Abbreviations

In the verbatim transcript, write numbers as spoken when practical.

Example:

`екі мың жиырма алтыншы жыл`

In normalized text, digits may be used if the project requires standardized formatting:

`2026 жыл`

Document the chosen convention and apply it consistently.

## 17. Translation

English translations should preserve meaning and tone, not force a word-for-word structure.

For code-switched speech:

- Preserve meaning across the full utterance.
- Note important cultural or pragmatic meaning.
- Avoid deleting hesitation or uncertainty when it affects interpretation.

## 18. Audio-Quality Labels

Evaluate the following separately:

- Background noise
- Clipping
- Reverberation
- Signal level
- Intelligibility
- Plosives
- Sibilance
- Distortion
- Editing artifacts
- Loudness consistency
- Frequency balance

Use a 1–5 scale:

- **5 — Excellent:** clean, natural, immediately usable
- **4 — Good:** minor defects, fully intelligible
- **3 — Usable with editing:** noticeable issues, recoverable
- **2 — Poor:** major issues, limited reliability
- **1 — Reject:** unsuitable for dependable annotation or model training

## 19. Training-Data Suitability Decision

Assign one outcome:

- **ACCEPT:** suitable without modification
- **ACCEPT_AFTER_EDITING:** usable after defined processing
- **REJECT:** quality or content is unreliable
- **ESCALATE:** requires a second reviewer or project-specific decision

The decision should include one sentence of rationale.

Example:

`ACCEPT_AFTER_EDITING — Speech is intelligible, but steady HVAC noise should be reduced before use.`

## 20. Confidence Scores

Use a segment-level confidence score from 0.00 to 1.00.

Recommended interpretation:

- `0.95–1.00`: clear and unambiguous
- `0.85–0.94`: minor uncertainty
- `0.70–0.84`: meaningful uncertainty; review recommended
- `<0.70`: do not guess; mark unclear, inaudible, or escalate

Confidence should reflect transcript certainty, not personal confidence in the language generally.

## 21. Quality-Control Workflow

Use the following review sequence:

1. **First listen:** understand the clip and identify languages.
2. **Verbatim pass:** transcribe exactly what is heard.
3. **Normalization pass:** create a readable normalized version.
4. **Linguistic review:** verify spelling, code-switching, names, and meaning.
5. **Audio review:** evaluate noise, clipping, reverberation, and intelligibility.
6. **Timestamp review:** confirm segment boundaries.
7. **Consistency review:** compare decisions against the guideline.
8. **Final review:** assign confidence and suitability decision.

## 22. Decision Log

Maintain a decision log for recurring ambiguous cases.

Recommended fields:

- Date
- Language
- Issue
- Example
- Decision
- Rationale
- Applies from version

Example:

| Issue | Decision | Rationale |
|---|---|---|
| English technical term with Kazakh suffix | Preserve spoken hybrid form | Reflects authentic code-switching |
| Audible filler before a sentence | Keep in verbatim, remove in normalized | Separates speech evidence from readable text |
| Uncertain word under noise | Use `[unclear]` | Avoids contaminating reference data |

## 23. Ethics and Privacy

- Use only recordings you own or have permission to share.
- Remove personal information when possible.
- Do not publish private conversations.
- Document whether samples are scripted, spontaneous, synthetic, or edited.
- Do not misrepresent AI-generated annotations as unreviewed human ground truth.
- Clearly state when a transcript was initially produced by ASR and then manually corrected.

## 24. Portfolio Disclosure

Recommended disclosure:

> These annotations were prepared as an independent portfolio demonstration. Automatic tools may have been used for initial segmentation or transcription, but all reference transcripts, linguistic judgments, and final quality decisions were manually reviewed.
