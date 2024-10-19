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

<div align="center">
  <img src="https://github.com/donkuri/lapis/raw/main/assets/fields.png" alt="Lapis fields">
  <p><em>Lapis fields</em></p>
</div>

**Your fields will not look exactly like this for two reasons**:

1. I use click cards and as such, there is an "x" in that field. **If you do not put anything in any of the "is...Card" field, the card will be a standard vocab card.** Choose whichever kind of card you want to use, maybe experiment a bit. Obviously, only fill one of these fields.
2. In `MainDefinition`, you will probably have to choose something else. For instance, if you use [Jitendex](https://jitendex.org/), you should select something like `{single-glossary-jitendex-something}`, where that something is probably a date depending on when you got Jitendex. What it does is select that dictionary to be used as the primary dictionary, and the rest of your dictionaries go into the glossaries (see the gif).
