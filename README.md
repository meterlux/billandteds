# Excellent GB

An iPhone-first Game Boy-style player for **Bill & Ted's Excellent Game Boy Adventure** (and any other original Game Boy cartridge you own). It runs entirely on the phone: add it to the Home Screen and it works full-screen and offline.

**No game is included.** Copy your own cartridge to a `.gb` file with a cartridge reader, put it in the iPhone Files app, and load it with the cartridge slot at the top-right. The repository ships only an openly licensed homebrew test cartridge (Porklike) so the shell can be tried before your dump is ready.

## Using it

- **Power**: the ◄OFF·ON► switch at the top-left. Power-on scrolls the logo stored in the loaded cartridge and plays the two-note start-up chime.
- **Cartridge**: the slot at the top-right (or the screen, while no cart is in). The loaded cart's title shows beside it, and it stays loaded on the phone. Loading a new cart powers the unit off first. Open the page with `#test` to load the bundled test cart.
- **Sound**: tap the speaker grille (bottom-right) to toggle sound on and off.
- **D-pad**: press anywhere on the left half. The direction follows your thumb, so drifting or a small reverse flick still steers. Diagonals are supported.
- **A / B**: press anywhere on the right half. Land on the seam between them to press both.
- **Leaving the app** freezes the game and saves your place; it picks up after the next start-up. Sliding the power **off** really is off: the next start is a fresh boot. Battery saves (if the cart has one) are always kept.
- On a computer: arrow keys, X = A, Z = B, Enter = Start, Shift = Select.

## Files

- `index.html`: the whole app (layout, LCD rendering, controls, start-up sequence, saving)
- `vendor/binjgb/`: the [binjgb](https://github.com/binji/binjgb) emulator core, prebuilt for the web (MIT, see its LICENSE)
- `carts/test-porklike.gb`: homebrew test cartridge from the binjgb demo, built with GB Studio (MIT, see `carts/LICENSE-porklike.txt`)
- `manifest.webmanifest`, `sw.js`, `icon-*.png`: Home Screen app and offline support

## Notes

- The start-up logo is read from the cartridge's own header, as the hardware does; no boot ROM is used. The chime is synthesized.
- Cartridge dumps and save files are ignored by git (`.gitignore`). Never commit them: this repository is public.
- Trade names are deliberately left off the shell.
