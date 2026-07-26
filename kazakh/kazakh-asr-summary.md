# Kazakh ASR Evaluation

## Summary

Whisper Small produced a partially intelligible transcription of the spontaneous Kazakh speech sample, but its overall accuracy was substantially lower than for the Russian recording. The model preserved the general subject of the recording—personal background, education, language experience, university studies, and engineering work—but introduced frequent lexical, morphological, orthographic, and named-entity errors.

Many phrases remained recognizable only because the human-reviewed reference transcript was available for comparison. Several words were replaced with phonetically similar but incorrect forms, and some longer phrases became difficult to interpret without native-speaker review.

The most serious errors occurred in proper nouns, educational terminology, inflected Kazakh words, and phrases involving multiple languages. Examples include `Атырау` being transcribed as `атрау`, `Батыс Қазақстанда` becoming `бәтсі қазақстанда`, and `Қазақ-Түрік лицейінде` becoming `қазақ тұрык лисенде`.

The result demonstrates that Whisper Small can preserve the broad topic of a Kazakh recording, but the output is not reliable enough for direct use as a final transcript. Extensive native-speaker correction is required.

## Key Errors

| Reference                                        | Whisper Output                             | Error Type                                                 |
| ------------------------------------------------ | ------------------------------------------ | ---------------------------------------------------------- |
| `Есімім Азат`                                    | `есмім азат`                               | Orthographic omission                                      |
| `Атырау қаласынан`                               | `атрау қаласынан`                          | Named-entity and vowel omission                            |
| `Батыс Қазақстанда`                              | `бәтсі қазақстанда`                        | Severe lexical substitution                                |
| `қазақ тілінің диалектісі батыстық деп саналады` | `қазақ тілдін диалекты бәстық деп саналад` | Morphology, spelling, and word-ending errors               |
| `Қазақ-Түрік лицейінде оқыдым`                   | `қазақ тұрык лисенде оқытым`               | Named-entity, lexical, and consonant-substitution errors   |
| `сол мектепте төрт тілде сабақ өткізді`          | `сөм ектепті түрц тілде саба құыткізді`    | Multiple substitutions and word-boundary errors            |
| `Орысша`                                         | `орша`                                     | Syllable deletion                                          |
| `Ағылшынша`                                      | `алшынша`                                  | Internal-syllable deletion                                 |
| `сол төрт тілдерді түсіне аламын`                | `сөм түрт тілдерді түсіне алам`            | Lexical substitution and ending deletion                   |
| `қолдана аламын`                                 | `құудан алам`                              | Severe lexical substitution                                |
| `Мектептен кейін`                                | `Мүктептен, кейен`                         | Vowel and spelling substitutions                           |
| `Арканзас штатындағы университетке түстім`       | `Арканзаштаттын униристет кетстім`         | Named-entity, segmentation, morphology, and lexical errors |
| `үшінші жылды бітірдім`                          | `үшінші жыл бытрыдым`                      | Vowel and consonant substitutions                          |
| `Осы жаз бір тағылымдама таптым`                 | `Осы жас бүр тахылым даматаптым`           | Word-boundary and lexical errors                           |
| `Литл-Рок қаласында`                             | `литуро қаласында`                         | Named-entity recognition error                             |
| `инженерлік жұмыс жасап жатырмын`                | `инженерелік жүміз жасып жатрымін`         | Morphology, vowel substitution, and spelling errors        |
| `сау болыңыздар`                                 | `сау бауныздар`                            | Lexical and morphological error                            |

## Error Patterns

### Named-Entity Recognition

Whisper had difficulty recognizing place names and institutional terms.

Examples include:

* `Атырау` → `атрау`
* `Арканзас` → `Арканзаштаттын`
* `Литл-Рок` → `литуро`
* `Қазақ-Түрік лицейі` → `қазақ тұрык лисен`

These errors are significant because they affect factual information about the speaker’s identity, education, and location.

### Kazakh Morphology

The model frequently dropped or altered Kazakh grammatical endings.

Examples include:

* `саналады` → `саналад`
* `аламын` → `алам`
* `жатырмын` → `жатрымін`
* `болыңыздар` → `бауныздар`
* `бітірдім` → `бытрыдым`

These errors often preserved part of the root word but produced grammatically incorrect forms.

### Lexical Substitution

Several words were replaced with unrelated or only loosely similar forms.

Examples include:

* `Батыс` → `бәтсі`
* `сол` → `сөм`
* `төрт` → `түрт` or `түрц`
* `қолдана` → `құудан`
* `жаз` → `жас`

Some substitutions remained phonetically similar, while others substantially reduced intelligibility.

### Word-Boundary and Segmentation Errors

Whisper sometimes merged or split words incorrectly.

Examples include:

* `Арканзас штатындағы` → `Арканзаштаттын`
* `тағылымдама таптым` → `тахылым даматаптым`
* `Қазақ-Түрік лицейінде` → `қазақ тұрык лисенде`

These segmentation errors made longer phrases particularly difficult to interpret.

### Multilingual Vocabulary

The section listing four languages was only partially recognized correctly.

The model correctly preserved recognizable forms of `қазақша` and `түрікше`, but it distorted:

* `Орысша` → `орша`
* `Ағылшынша` → `алшынша`

This suggests that familiar language names were not consistently recognized even when spoken in a clearly structured list.

## Severity Assessment

The Kazakh transcription required substantial human correction.

The errors can be grouped by severity:

* **Minor:** capitalization, punctuation, and small spelling differences
* **Moderate:** missing suffixes, altered vowels, and recognizable word substitutions
* **Major:** incorrect place names, distorted educational terminology, merged phrases, and replacements that changed or obscured meaning

The transcript preserved the general progression of the speech, but many individual sentences were not dependable without access to the original recording and a native-speaker reference.

## Comparison with Russian

Whisper Small performed noticeably worse on the Kazakh recording than on the Russian recording.

The Russian transcript contained several meaningful errors, but most sentences remained readable and the overall wording was largely preserved. In contrast, the Kazakh output contained frequent errors across nearly every sentence, including severe distortions of common phrases and proper nouns.

This comparison suggests that the same multilingual model and recording setup can produce substantially different results depending on the language.

## Human Review

Native-speaker review was essential for this sample. The reviewer corrected:

* Place names
* Educational terminology
* Kazakh grammatical endings
* Language names
* Word boundaries
* Lexical substitutions
* Personal and factual details

Without a human-reviewed reference transcript, several ASR segments could have been interpreted incorrectly.

## Conclusion

Whisper Small retained the broad topic and approximate sequence of the Kazakh recording, but it did not produce a sufficiently accurate transcript for direct use.

The model struggled most with Kazakh morphology, proper nouns, institutional names, word segmentation, and longer multiword phrases. The output required extensive native-speaker correction, demonstrating the importance of human evaluation for lower-resource multilingual speech-recognition systems.

## Included Files

* `kazakh-raw.wav`
* `kazakh-processed.wav`
* `kazakh-sample-metadata.md`
* `kazakh-whisper-output.json`
* `kazakh-transcript-comparison.md`
