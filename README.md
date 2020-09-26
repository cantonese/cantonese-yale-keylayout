# Cantonese Yale Keyboard Input for macOS

This repo has a configuration file for "dead key" input of Yale Romanization tone marks based on the default macOS US English keyboard.

## Usage

The key chords are:
- **Option + 1, (AEGIMOU)**: High tone, `¯`. (Replaces `¡`)
- **Option + 2, (AEGIMOU)**: High rising tone, `´`. (Replaces `™`)
- **Option + 4, (AEGIMOU)**: Low falling tone, `` ` ``. (Replaces `¢`)
- **Option + 5, (AEGIMOU)**: Low rising tone, `´`. (Replaces `∞`)

There is no distinction between **Option + 2** and **Option + 5** output; they're both present in order to train remembering of tones.

## Installation

```bash
sudo ln -s $PWD/Yale.keylayout /Library/Keyboard\ Layouts/
sudo ln -s $PWD/Yale.icns /Library/Keyboard\ Layouts/
```

## Population

Simple helper script I wrote to make sure I got it right.

```javascript
function getValues(root){
  return `
    <when state="Tone1Entry" output="${root}\u0304"/>
    <when state="Tone2Entry" output="${root}\u0301"/>
    <when state="Tone4Entry" output="${root}\u0300"/>
    <when state="Tone5Entry" output="${root}\u0301"/>`.normalize();
}

copy(getValues('a'));
```
