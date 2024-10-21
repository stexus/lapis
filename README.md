# Lapis

An advanced yet lightweight [Anki](https://apps.ankiweb.net/) notetype, thoughtfully designed to be fast, feature-rich, and fully backwards compatible. 

<div align="center">
  <img src="https://github.com/donkuri/lapis/raw/main/assets/Lapis.gif" alt="Click cards with Lapis">
  <p><em>Click cards with Lapis, the anime's Shōshimin Series</em></p>
</div>

### Table of Contents

- [Why Yet Another Anki Notetype?](#why-yet-another-anki-notetype?)
- [Key Features](#key-features)
- [How to use the Card](#how-to-use-the-card)
- [Credits](#credits)
- [FAQ](#faq)
-
## Why Yet Another Anki Notetype?

Great question. The answer? To address issues found in an older notetype called JPMN, originally created by Aquafina and now maintained by arbyste. Here’s a quick rundown of some of those problems:

1. The note relied on custom handlebars, many of which are now redundant thanks to direct implementation in Yomitan.
2. The heavy use of JavaScript on the card caused noticeable lag, especially for users on mobile devices.
3. Its dependency on handlebars meant it wasn’t compatible with tools that don’t support Yomitan or handlebars directly, like [JL](https://github.com/rampaa/JL).
4. JPMN's dependency on it's own custom handlebars and use of CSS to format definitions meant it didn’t support every dictionary and could occasionally break formatting in rare corner cases, though these instances were uncommon.
5. The source code was machine-generated, making it a real challenge for both developers and non-developers alike to read and customize.

To tackle these issues, Donkuri and Ruri teamed up to create a new notetype. It combines the best features of JPMN and another excellent notetype, [rudnam's JP-study](https://github.com/rudnam/JP-study). Ruri focused on the technical side, while Donkuri helped with design, suggested changes, and led the project. **By the way, we're always open to new contributors!**

## Key features

- This card **doesn’t rely on custom handlebars** at all, meaning it fully supports every Japanese dictionary that Yomitan does, and the chance of something breaking is exceptionally rare.  
- You can easily select different types of cards using the `Is...Card` selectors—just add a simple 'x' to the field you want for that specific card type. If you ever need to switch card types for many notes at once, you can use [Batch Editing](https://ankiweb.net/shared/info/291119185) to make the change quickly.
- Lapis also lets you sort Japanese words by frequency, either manually using [Advanced Browser](https://ankiweb.net/shared/info/874215009) to view the frequencies calculated in `FreqSort`, or automatically with [AutoReorder](https://ankiweb.net/shared/info/757527607). **However, it's not recommended to use AutoReorder, as there have been cases where the addon resets learned cards to 'new'.**
- It allows you to organizes dictionaries into different fields, making it easier to view information in an organized manner. You can easily choose which dictionaries you'd like to see (more details [below](#how-to-use-the-card)).

## How to use the card

To use the card, first download the example deck from Releases. From there, you need to change your fields settings in Yomitan. First select `Lapis` for the `Model` in your Yomitan's `Configure Anki Card Format`. Here's how your fields should be set up:

| Field              | Value                                              |
| ------------------ | -------------------------------------------------- |
| Expression         | `{expression}`                                     |
| ExpressionFurigana | `{furigana-plain}`                                 |
| ExpressionReading  | `{reading}`                                        |
| ExpressionAudio    | `{audio}`                                          |
| SelectionText      | `{popup-selection-text}`                           |
| MainDefinition     | Something like `{single-glossary-jmdict/jitendex}` |
| Sentence           | `{cloze-prefix}<b>{cloze-body}</b>{cloze-suffix}`  |
| SentenceFurigana   |                                                    |
| SentenceAudio      |                                                    |
| Picture            |                                                    |
| Glossary           | `{glossary}`                                       |
| Hint               |                                                    |
| IsHintCard         |                                                    |
| IsClickCard        |                                                    |
| IsSentenceCard     |                                                    |
| PitchPosition      | `{pitch-accent-positions}`                         |
| Frequency          | `{frequencies}`                                    |
| FreqSort           | `{frequency-harmonic-rank}`                        |
| MiscInfo           |                                                    |


## Credits

I’d like to express my heartfelt thanks to everyone who made this notetype possible. First, a huge thank you to [Donkuri](https://github.com/donkuri/) for agreeing to collaborate with me on this project. I’ve learned so much thanks to you, and the notetype has improved far more than it ever could have without your help—thank you, truly, from the bottom of my heart.

Next, I’d like to thank [Rudnam](https://github.com/rudnam/), whose code laid the foundation for this project. Your clear, functional code made everything so much easier, and your entire logic code (with some modifications) is showcased in Lapis!

Finally, a big thank you to [Aquafina (Austin S.)](https://github.com/Aquafina-water-bottle) and [Arbyste](https://github.com/arbyste) for creating and maintaining JPMN, which inspired the UI for Lapis. Your work laid the groundwork for what this project has become.

Last but not least, there’s me, Ruri! I wrote the code (and spent countless hours troubleshooting when things didn’t work the way I expected). I’ve done my best to make the code clear and easy to understand for anyone who wants to contribute—so a big thanks in advance to those who do!

## FAQ

### How do I setup AJT Japanese to work with Lapis?

Please refer to [this](docs/anki_setup.md)

### How do I setup mining workflow for different media with Lapis in regard?

For that, please go through [Donkuri's Mining Setups](https://donkuri.github.io/learn-japanese/mining/).

### How do I use different card types?

The `is...Card` fields let you select the kind of card you want to use. Without anything, you get plain old vocab cards. Hint cards let you have a hint in front, click cards let you click on the word in the front of the card to get the sentence, and sentence cards are cards where the sentence is directly in the front of the card.

### What is the purpose of the three different fields for definitions?

This is partly inspired by JPMN and its method of organizing dictionaries. There are three main fields:

- `SelectionText` – Use this when you want to highlight a specific sentence or definition from the Yomitan popup. If you don’t need to highlight anything, just leave it empty—it won’t affect the notetype.
- `MainDefinition` – This is where you input the main dictionary you prefer. I highly recommend filling this in. If you're new to Japanese or mining on your own, it’s a good idea to start with a bilingual dictionary like JMDict/Jitendex. Alternatively, you can use your preferred monolingual dictionaries (such as 三省堂, 大辞林, 大辞泉, or 新明解) by selecting them when configuring Yomitan. **Please note, the dictionaries need to be installed in Yomitan before they can be selected.**
- `Glossary` – This is where you place all of your dictionary definitions. I strongly suggest using more than one dictionary—ideally a bilingual main dictionary along with 3-5 monolingual dictionaries. You can read more about best practices for learning Japanese in [Donkuri's guide](https://donkuri.github.io/learn-japanese/). **However, if you choose to use only a single dictionary, make sure it’s selected in `MainDefinition` and leave this field EMPTY to avoid a known bug.**

### I found a bug!! Help!!!

Fret not, if you would like to report a bug or an issue with the card, please open an issue and we would be more than happy to help you!

### I found a bug! There's a weird `yomitan` tag at the bottom of my card!! Help!!!

No worries! This is an easy fix. Just make sure the `Card tags` in your Yomitan settings is empty, as it’s usually filled with `yomitan` by default, which causes this issue, The notetype displays all tags on the note at the bottom of the card, which can actually be useful for marking the source of the card. For example, if you get a card from Releases, you might see a tag like アニメ:小市民シリーズ at the bottom, indicating the source. **These tags aren’t added automatically—you'll need to apply them manually if you want them. If you don't apply any tag, nothing will be rendered at the bottom, and that's perfectly fine too.** 

### How do I add a note to the card?

You can use the `MiscInfo` field to add any extra information you'd like. Then it would appear at the bottom of the back of the card.

### Why do you use `{frequency-harmonic-rank}`  in FreqSort?

`{frequency-harmonic-rank}` calculates the [harmonic mean](https://en.wikipedia.org/wiki/Harmonic_mean) of all the frequency dictionaries you have installed in Yomitan. This is very effective as it calculates what a word's *true frequency* might be. For dictionaries, please refer to [shoui Yomichan Dictionaries Collection](https://learnjapanese.link/dictionaries) and [Yomitan Dictionaries](https://github.com/MarvNC/yomitan-dictionaries) by [Marv](https://github.com/MarvNC).

### What Japanese Guides do you recommend to learn through?

These guides are recommended: 
- [Immersion Based Japanese Learning](https://donkuri.github.io/learn-japanese/) by Donkuri
- [TheMoeWay](https://learnjapanese.moe/) by Shoui. I also recommend joining their [Discord Server](https://learnjapanese.moe/join/)

### How can I change the font size for something?

To change the font size, open the `Styling` section of the card in Anki by going to `Browse` → Select a Lapis card → Click `Cards` (top-left of the card editor). Once there, look for the section at the top labeled `/* PC Font sizes */` or `/* Mobile font sizes */`, which looks like this:

```css
  /* PC Font sizes */
  --pc-main-font-size: 16px;
  --pc-main-def-size: 20px;
  --pc-vocab-font-size: 85px;
  --pc-back-vocab-font-size: 60px;
  --pc-sentence-font-size: 52px;
  --pc-back-sentence-font-size: 35px;
  --pc-hint-font-size: 38px;
  --pc-info-font-size: 23px;

  /* Mobile font sizes */
  --mobile-main-font-size: 16px;
  --mobile-main-def-size: 16px;
  --mobile-vocab-font-size: 70px;
  --mobile-back-vocab-font-size: 32px;
  --mobile-sentence-font-size: 38px;
  --mobile-back-sentence-font-size: 24px;
  --mobile-hint-font-size: 24px;
  --mobile-info-font-size: 16px;
```

You can adjust any of these `px` values to your preferred font size.

### How do I use my own font?

To change the font family, open the `Styling` section of the card in Anki by going to `Browse` → Select a Lapis card → Click `Cards` (top-left of the card editor). In the `Styling` section, look for the part labeled `/* Miscellaneous */`, and you’ll see this:

```css
  --font-serif: serif;
  --font-sans: sans-serif;
``` 

You can replace these with any fonts you prefer, or leave it as is to use your OS's default fonts. However, to avoid having Chinese fonts display Japanese kanji (since we're learning Japanese), make sure to read through [this guide](https://learnjapanese.moe/font/).

It’s a good idea to choose fonts you like, as you’ll be using them for a long time while learning. If you’re unsure and don’t want to stick with your system’s default fonts, try using Noto CJK or Hiragino fonts (Hiragino is default on macOS).

### I have a question that’s not in the FAQs!

No problem! Feel free to open an issue with your specific question.

### Will this work with tools like JL?

At the moment, Ruri is still working on understanding the details of JL and related tools. However, due to time constraints, answering this question may take a little longer (sorry for the delay!).
