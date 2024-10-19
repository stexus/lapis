# Lapis
Lapis is a modern [Anki](https://apps.ankiweb.net/) notetype designed with compatibility in mind. It was made to look like [arbyste's JPMN](https://arbyste.github.io/jp-mining-note-prerelease/) but fix three main issues we found with the note:

1. The note uses custom handlebars. Some of these are no longer necessary because they were directly implemented in Yomitan.
2. Due to the heavy amount of JavaScript on the card, it is laggy for many people on mobile devices.
3. Due to the direct dependency on handlebars, it is not compatible with other tools that do not support Yomitan or handlebars directly, such as [JL](https://github.com/rampaa/JL).

For all these reasons, [ruri](link-to-ruris-github) and myself decided to work on a new notetype that would emulate many features from both JPMN and another fantastic notetype, [rudnam's JP-study](https://github.com/rudnam/JP-study). Most of the technical details were left to him (thank you!), while I helped design the card, suggest changes and lead the project. **We are always looking for contributors!**

<img src="https://github.com/donkuri/lapis/raw/main/assets/Lapis.gif" alt="Click cards with Lapis" style="width:50%;">

