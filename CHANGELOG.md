# Changelog

Notable changes to this card. The version shown in the editor toolbar (`v…`) matches the release tag.

## [0.9.61] – 2026-10-26

### Added

- Interface available in **German** and **English**; French stays the source language and the fallback for every other language.
- Language follows the Home Assistant profile (`hass.language`), including regional variants (`de-AT` → `de`, `en-GB` → `en`).
- New card option `language: fr | de | en` to force a language, for example on a dashboard shared between accounts.
- Changing the profile language rebuilds the card and its editor without reloading the page.

### Changed

- Messages that were assembled by string concatenation now use `{placeholder}` templates, as the Home Assistant translation rules require (never build a sentence from separately translated pieces).
- The device list in the bubble panel is sorted in the current language.
- The card-picker description is now English: it is registered once, before `hass` exists, so it cannot follow the profile language.
- `README.md` is English from now on; the French documentation moved to `README_fr.md`.

### Notes

- Default behaviour is unchanged: a French profile, an unknown language, or a card that has not received `hass` yet all show French.
- Every text lives in `TPC_STRINGS` at the top of `tile-placer-card.js`; adding a language means adding one table of that shape.
- Configuration errors raised by `setConfig` stay French, because they can be thrown before `hass` is available.

## Earlier versions

Versions up to `0.9.60` predate this changelog; see the [releases](../../releases).
