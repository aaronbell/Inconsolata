# Inconsolata

Open-source monospace font for code listings, originally by [**@raphlinus**](https://github.com/raphlinus/)

### Ligatures

Inconsolata includes ligatures for a few JavaScript operators:

<img
  src = "./documentation/img/ligature-sample.png"
  alt = "Ligatures sample"
  width = "404" height = "276"
/>

- **"Inconsolata"** exposes the ligatures as `dlig`.  These are disabled by default, and probably won't show up in your editor.  You can enable them in CSS with this rule:
   ```css
  font-variant-ligatures: discretionary-ligatures;
  ```

(*note* for the purposes of this repository, Ligconsolata has been disabled)

## Building

Fonts are built automatically by GitHub Actions - take a look in the "Actions" tab for the latest build.

If you particularly want to build fonts manually on your own computer, you will need to install the [`yq` utility](https://github.com/mikefarah/yq). On OS X with Homebrew, type `brew install yq`; on Linux, try `snap install yq`; if all else fails, try the instructions on the linked page.

Then:

* `make build` will produce font files.
* `make test` will run [FontBakery](https://github.com/googlefonts/fontbakery)'s quality assurance tests.
* `make proof` will generate HTML proof files.

Note – if you update the source files, they must be prepped before the build will accept them:

To prep the source we must load sources/Inconsolata-source.glyphs in Glyphs and do the following:
- Run the decompose-transformed-components.py script
- Run the gen_instances.py script
- Run the inco_fix.py script
- Save the file in the sources directory with the filename "Inconsolata.glyphs"

## License

This Font Software is licensed under the SIL Open Font License, Version 1.1.
This license is copied below, and is also available with a FAQ at
http://scripts.sil.org/OFL

## Changelog v.3.000

Upgrade to 2-axis variable font family, with widths from 50 to 200, and weights from 200 to 900.

## Changelog v.2.013

- Removed ligatures for `fi` and `fl`.
- Operator ligatures moved to `dlig`.
- New variant "Ligconsolata" introduced, which exposes operator ligatures as `liga`.

## Changelog v.2.011

March 2018 glyph set expansion was completed by [**@appsforartists**](https://github.com/appsforartists/), which included:

- [x] Glyph Set expanded to include ligatures for ===, !==, =>, <=, >=, ->, <-

## Changelog v.2.001

August 2016 glyph set expansion was completed by Alexei Vanyashin ( [Cyreal][5] ), which included:

- [x] Glyph Set expanded to GF Latin Pro
- [x] Additional glyphs ⊕↑↗→↘↓↙←↖↔↕⇧⇨⇩⇦⬆⮕⬇⬅●○◆◇☹☺☻♠♣♥♦✓✔✕✗✘␣⎋⌂⇪⌧⌫⌦⌥⌘⏎�
- [x] Minor design improvements (trademark corner spurs)

Further reading: Inconsolata expansion project thread on [Google Fonts Discussions][6]

#### Supported glyphs sets:

* GF Latin Pro

![Inconsolata Preview](documentation/img/inco-preview.png)

### Future work

In addition, we want to export a subset not including Vietnamese script coverage, to avoid over-large line spacing on older applications (such as terminals and text editors) that don't understand the "use typo metrics" flag (see https://github.com/googlefonts/Inconsolata/issues/35).

## Glyphstool

The repository also contains some Rust code to manipulate Glyphs format masters, in the `glyphstool` subdirectory. This was used to apply global transforms (mostly as a starting point for the width work). Perhaps the most valuable aspect is that it contains a fairly complete set of line and box drawing primitives, inspired by [Source Code Pro] but with actually variable weight and width. It's not particularly polished or well documented, but is provided for completeness, and it's possible that it could be adapted to future tools that work with font data in the Glyphs format. The code is licensed under Apache 2.0 or MIT, in keeping with the Rust tradition.

----

## Copyright

Copyright 2006 The Inconsolata Project Authors

## Links

* [Inconsolata on Google Fonts][1]
* [Inconsolata on Levien.com][2]
* [Official Upstream on git][3]

[1]: https://fonts.google.com/specimen/Inconsolata
[2]: http://levien.com/type/myfonts/inconsolata.html
[3]: https://github.com/google/fonts/tree/master/ofl/inconsolata
[4]: http://scripts.sil.org/OFL
[5]: http://cyreal.org
[6]: https://groups.google.com/forum/#!searchin/googlefonts-discuss/inconsolata%7Csort:relevance/googlefonts-discuss/wgVuOx9yo5k/2QSUQ78CCQAJ
[fontmake]: https://github.com/googlefonts/fontmake
