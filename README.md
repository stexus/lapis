# Lapis
Lapis is a modern [Anki](https://apps.ankiweb.net/) notetype designed with compatibility in mind. 

<div align="center">
  <img src="https://github.com/donkuri/lapis/raw/main/assets/Lapis.gif" alt="Click cards with Lapis">
  <p><em>Click cards with Lapis</em></p>
</div>

It was made to look like [arbyste's JPMN](https://arbyste.github.io/jp-mining-note-prerelease/) but fix three main issues we found with the note:

1. The note uses custom handlebars. Some of these are no longer necessary because they were directly implemented in Yomitan.
2. Due to the heavy amount of JavaScript on the card, it is laggy for many people on mobile devices.
3. Due to the direct dependency on handlebars, it is not compatible with other tools that do not support Yomitan or handlebars directly, such as [JL](https://github.com/rampaa/JL).

For all these reasons, [ruri](link-to-ruris-github) and myself decided to work on a new notetype that would emulate many features from both JPMN and another fantastic notetype, [rudnam's JP-study](https://github.com/rudnam/JP-study). Most of the technical details were left to him (thank you!), while I helped design the card, suggest changes and lead the project. **We are always looking for contributors!**

## How to use the card

To use the card, first download the example deck. From there, you need to change your fields settings in Yomitan. Here is a picture showing how the fields should be set up:


| Field              | Value                                             |
| ------------------ | ------------------------------------------------- |
| Expression         | `{expression}`                                    |
| ExpressionFurigana | `{furigana-plain}`                                |
| ExpressionReading  | `{reading}`                                       |
| ExpressionAudio    | `{audio}`                                         |
| SelectionText      |  `{popup-selection-text}`                         |
| MainDefinition     | `{single-glossary-jmdict/jitendex}`               |
| Sentence           | `{cloze-prefix}<b>{cloze-body}</b>{cloze-suffix}` |
| SentenceFurigana   |                                                   |
| SentenceAudio      |                                                   |
| Picture            |                                                   |
| Glossary           | `{glossary}`                                      |
| Hint               |                                                   |
| IsHintCard         |                                                   |
| IsClickCard        |                                                   |
| IsSentenceCard     |                                                   |
| PitchPosition      | `{pitch-accent-positions}`                        |
| Frequency          | `{frequencies}`                                   |
| FreqSort           | `{frequency-harmonic-rank}                        |
| MiscInfo           |                                                   |
| ExtraField         |                                                   |

**Notes:**

1. There `is...Card` fields let you select the kind of card you want to use. Without anything, you get plain old vocab cards. Hint cards let you have a hint in front, click cards let you click on the word in the front of the card to get the sentence (what I use personally), and sentence cards are cards where the sentence is directly in the front of the card.
2. In `MainDefinition`, you will probably have to choose something. For instance, if you use [Jitendex](https://jitendex.org/), you should select something like `{single-glossary-jitendex-something}`, where that something is probably a date depending on when you got Jitendex. If you use [JMdict](https://github.com/yomidevs/jmdict-yomitan/releases), it'll be `{single-glossary-jmdict-something}`, as above. What it does is select that dictionary to be used as the primary dictionary, and the rest of your dictionaries go into the glossaries (see the gif).
