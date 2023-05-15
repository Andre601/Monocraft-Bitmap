# Monocraft-Bitmap

Monocraft-Bitmap (Referred to as just "Monocraft" in Minecraft itself) is a PNG (Bitmap) based font inspired by the original [Monocraft] font by [IdreesInc].  
Its main aim is to provide a monospaced font usable inside Minecraft Resource packs either as replacement of the default font or by using the `font` option in JSON components.

## Fonts

This resource provides a `default.json` file allowing you to use the font through `monocraft:default` inside a `font` option in JSON components.

### Coverage

The following files are currently being covered:

- `ascii.png` (Alphanummerical characters and some special ones)
- `nonlatin_european.png` (Special characters and unicode emojis)

Please note any information in [Current Limitations and Issues](#current-limitations-and-issues).

## How it works

Minecrafts way of creating and using fonts does not allow empty spaces before and after a font (No leading or trailing empty pixels). This is best shown with one pixel wide characters like `i` or `!`.  
This, as you may guess, would make this font non-monospaced.

To bypass this restriction did I simply add semi-transparent pixels (7% opacity in Gimp) to "pad out" the character itself. The semi-transparent pixels are not really visible inside the chat or anywhere really, while the width is kept.

## How to use

To add this font to your client/server, move the contents of `assets/monocraft/` into your own resource pack like this:
```
assets/
└── monocraft/
    ├── font/
    │   └── default.json
    └── textures/
        └── font/
            ├── ascii.png
            └── nonlatin_european.png
```
This would already allow you to use the font through the `font` option of JSON components (i.e. `/tellraw @a {"text": "Hello world!", "font": "monocraft:default"}`).  
If you want to use this font by default (Replace the Minecraft font), move the `default.json` file from `assets/monocraft/font/` to a directory called `assets/minecraft/font/`. This will override the existing default font of Minecraft.

## Current Limitations and Issues

There are currently a few limitations and issues that I (Andre_601) can't solve on my own, which is why I would appreciate any help to get this stuff going.

- The font does not have a 100% monospacing right now. Some characters (Especially unicode emojis) do not have a proper monspaced width (Usually 5px). I'm currently debating on increasing the width or otherwise trying to find good looking designs for the characters.
- None of the `unicode_<x>.png` are covered yet. I'm not entirely sure if they are worth the effort to implement.

## Licenses

This project is licensed under [MIT][license].  
For the sake of transparency (And out of respect) is the original OFL (Open font license) of the Monocraft Font [also included][monocraft-license] even tho no original font file is being included in this repository.

[Monocraft]: https://github.com/IdreesInc/Monocraft
[IdreesInc]: https://github.com/IdreesInc

[license]: https://github.com/Andre601/Monocraft-Bitmap/blob/main/LICENSE
[monocraft-license]: https://github.com/Andre601/Monocraft-Bitmap/blob/main/MONOCRAFT%20OFL%20LICENSE